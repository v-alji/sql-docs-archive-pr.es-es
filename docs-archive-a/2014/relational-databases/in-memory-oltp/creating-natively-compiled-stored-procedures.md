---
title: Creación de procedimientos almacenados compilados de forma nativa | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: e6b34010-cf62-4f65-bbdf-117f291cde7b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3e8e8139427c7f2ad92eea856be8da542f65e344
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670383"
---
# <a name="creating-natively-compiled-stored-procedures"></a><span data-ttu-id="c1c75-102">Crear procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="c1c75-102">Creating Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="c1c75-103">Los procedimientos almacenados compilados de forma nativa no implementan el área expuesta completa de programación y consulta de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c1c75-103">Natively compiled stored procedures do not implement the full [!INCLUDE[tsql](../../includes/tsql-md.md)] programmability and query surface area.</span></span> <span data-ttu-id="c1c75-104">Hay ciertas construcciones de [!INCLUDE[tsql](../../includes/tsql-md.md)] que no se pueden usar en los procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="c1c75-104">There are certain [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs that cannot be used inside natively compiled stored procedures.</span></span> <span data-ttu-id="c1c75-105">Para obtener más información, vea [construcciones admitidas en procedimientos almacenados compilados de forma nativa](../in-memory-oltp/supported-features-for-natively-compiled-t-sql-modules.md).</span><span class="sxs-lookup"><span data-stu-id="c1c75-105">For more information, see [Supported Constructs in Natively Compiled Stored Procedures](../in-memory-oltp/supported-features-for-natively-compiled-t-sql-modules.md).</span></span>  
  
 <span data-ttu-id="c1c75-106">Sin embargo, hay varias características de [!INCLUDE[tsql](../../includes/tsql-md.md)] que se admiten solo para los procedimientos almacenados compilados de forma nativa:</span><span class="sxs-lookup"><span data-stu-id="c1c75-106">There are, however, several [!INCLUDE[tsql](../../includes/tsql-md.md)] features that are only supported for natively compiled stored procedures:</span></span>  
  
-   <span data-ttu-id="c1c75-107">Bloques atomic.</span><span class="sxs-lookup"><span data-stu-id="c1c75-107">Atomic blocks.</span></span> <span data-ttu-id="c1c75-108">Para obtener más información, consulte [Atomic Blocks](atomic-blocks-in-native-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c1c75-108">For more information, see [Atomic Blocks](atomic-blocks-in-native-procedures.md).</span></span>  
  
-   <span data-ttu-id="c1c75-109">Restricciones `NOT NULL` en los parámetros y variables de los procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="c1c75-109">`NOT NULL` constraints on parameters of and variables in natively compiled stored procedures.</span></span> <span data-ttu-id="c1c75-110">No se pueden asignar valores `NULL` a los parámetros o variables declarados como `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="c1c75-110">You cannot assign `NULL` values to parameters or variables declared as `NOT NULL`.</span></span> <span data-ttu-id="c1c75-111">Para obtener más información, vea [DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c1c75-111">For more information, see [DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql).</span></span>  
  
-   <span data-ttu-id="c1c75-112">Enlace de esquema de los procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="c1c75-112">Schema binding of natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="c1c75-113">Los procedimientos almacenados compilados de forma nativa se crean por medio de [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c1c75-113">Natively compiled stored procedures are created using [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span> <span data-ttu-id="c1c75-114">En el ejemplo siguiente se muestra una tabla optimizada para memoria y un procedimiento almacenado compilado de nativa que se usa para insertar filas en la tabla.</span><span class="sxs-lookup"><span data-stu-id="c1c75-114">The following example shows a memory-optimized table and a natively compiled stored procedure used for inserting rows into the table.</span></span>  
  
```sql  
create table dbo.Ord  
(OrdNo integer not null primary key nonclustered,   
 OrdDate datetime not null,   
 CustCode nvarchar(5) not null)   
 with (memory_optimized=on)  
go  
  
create procedure dbo.OrderInsert(@OrdNo integer, @CustCode nvarchar(5))  
with native_compilation, schemabinding, execute as owner  
as   
begin atomic with  
(transaction isolation level = snapshot,  
language = N'English')  
  
  declare @OrdDate datetime = getdate();  
  insert into dbo.Ord (OrdNo, CustCode, OrdDate) values (@OrdNo, @CustCode, @OrdDate);  
end  
go  
```  
  
 <span data-ttu-id="c1c75-115">En el ejemplo de código, `NATIVE_COMPILATION` indica que este procedimiento almacenado de [!INCLUDE[tsql](../../includes/tsql-md.md)] es un procedimiento almacenado compilado de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="c1c75-115">In the code sample, `NATIVE_COMPILATION` indicates that this [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure is a natively compiled stored procedure.</span></span> <span data-ttu-id="c1c75-116">Se requieren las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c1c75-116">The following options are required:</span></span>  
  
|<span data-ttu-id="c1c75-117">Opción</span><span class="sxs-lookup"><span data-stu-id="c1c75-117">Option</span></span>|<span data-ttu-id="c1c75-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1c75-118">Description</span></span>|  
|------------|-----------------|  
|`SCHEMABINDING`|<span data-ttu-id="c1c75-119">Los procedimientos almacenados compilados de forma nativa se debe enlazar al esquema de objetos al que hacen referencia.</span><span class="sxs-lookup"><span data-stu-id="c1c75-119">Natively compiled stored procedures must be bound to the schema of the objects it references.</span></span> <span data-ttu-id="c1c75-120">Esto significa que no se puede anular la tabla a la que hace referencia el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c1c75-120">This means that table references by the procedure cannot be dropped.</span></span> <span data-ttu-id="c1c75-121">Las tablas a las que se hace referencia en el procedimiento deben incluir el nombre de esquema y \* no se permiten caracteres comodín () en las consultas.</span><span class="sxs-lookup"><span data-stu-id="c1c75-121">Tables referenced in the procedure must include their schema name, and wildcards (\*) are not allowed in queries.</span></span> <span data-ttu-id="c1c75-122">`SCHEMABINDING` solo se admite para los procedimientos almacenados compilados de forma nativa en esta versión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1c75-122">`SCHEMABINDING` is only supported for natively compiled stored procedures in this version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>|  
|`EXECUTE AS`|<span data-ttu-id="c1c75-123">Los procedimientos almacenados compilados de forma nativa no admiten `EXECUTE AS CALLER`, que es el contexto de ejecución predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c1c75-123">Natively compiled stored procedures do not support `EXECUTE AS CALLER`, which is the default execution context.</span></span> <span data-ttu-id="c1c75-124">Por tanto, se deberá especificar el contexto de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c1c75-124">Therefore, specifying the execution context is required.</span></span> <span data-ttu-id="c1c75-125">`EXECUTE AS OWNER`Se admiten las opciones, el `EXECUTE AS` *usuario*y `EXECUTE AS SELF` .</span><span class="sxs-lookup"><span data-stu-id="c1c75-125">The options `EXECUTE AS OWNER`, `EXECUTE AS`*user*, and `EXECUTE AS SELF` are supported.</span></span>|  
|`BEGIN ATOMIC`|<span data-ttu-id="c1c75-126">El cuerpo de un procedimiento almacenado compilado de forma nativa debe constar exactamente de un solo bloque atomic.</span><span class="sxs-lookup"><span data-stu-id="c1c75-126">The natively compiled stored procedure body must consist of exactly one atomic block.</span></span> <span data-ttu-id="c1c75-127">Los bloques atomic garantizan la ejecución atómica del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="c1c75-127">Atomic blocks guarantee atomic execution of the stored procedure.</span></span> <span data-ttu-id="c1c75-128">Si se invoca el procedimiento fuera del contexto de una transacción activa, iniciará una nueva transacción, que se confirma al final del bloque atomic.</span><span class="sxs-lookup"><span data-stu-id="c1c75-128">If the procedure is invoked outside the context of an active transaction, it will start a new transaction, which commits at the end of the atomic block.</span></span> <span data-ttu-id="c1c75-129">Los bloques atomic de los procedimientos almacenados compilados de forma nativa tienen dos opciones obligatorias:</span><span class="sxs-lookup"><span data-stu-id="c1c75-129">Atomic blocks in natively compiled stored procedures have two required options:</span></span><br /><br /> <span data-ttu-id="c1c75-130">`TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="c1c75-130">`TRANSACTION ISOLATION LEVEL`.</span></span> <span data-ttu-id="c1c75-131">Vea [niveles](../../database-engine/transaction-isolation-levels.md) de aislamiento de transacción para los niveles de aislamiento admitidos.</span><span class="sxs-lookup"><span data-stu-id="c1c75-131">See [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md) for supported isolation levels.</span></span><br /><br /> <span data-ttu-id="c1c75-132">`LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="c1c75-132">`LANGUAGE`.</span></span> <span data-ttu-id="c1c75-133">El lenguaje del procedimiento almacenado se debe establecer en uno de los lenguajes o de alias de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="c1c75-133">The language for the stored procedure must be set to one of the available languages or language aliases.</span></span>|  
  
 <span data-ttu-id="c1c75-134">En relación con `EXECUTE AS` y los inicios de sesión de Windows, puede aparecer un error debido a la suplantación realizada con `EXECUTE AS`.</span><span class="sxs-lookup"><span data-stu-id="c1c75-134">Regarding `EXECUTE AS` and Windows logins, an error can occur because of the impersonation done through `EXECUTE AS`.</span></span> <span data-ttu-id="c1c75-135">Si una cuenta de usuario usa la autenticación de Windows, debe haber plena confianza entre la cuenta de servicio utilizada para la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y el dominio del inicio de sesión de Windows.</span><span class="sxs-lookup"><span data-stu-id="c1c75-135">If a user account uses Windows Authentication, there must be full trust between the service account used for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance and the domain of the Windows login.</span></span> <span data-ttu-id="c1c75-136">Si no hay plena confianza, se devuelve el siguiente mensaje de error al crear un procedimiento almacenado compilado de forma nativa: mensaje 15404, no se pudo obtener información acerca del grupo o usuario de Windows NT ' nombredeusuario '; código de error 0X5.</span><span class="sxs-lookup"><span data-stu-id="c1c75-136">If there is not full trust, the following error message is returned when creating a natively compiled stored procedure: Msg 15404, Could not obtain information about Windows NT group/user 'username', error code 0x5.</span></span>  
  
 <span data-ttu-id="c1c75-137">Para resolver este error, utilice uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c1c75-137">To resolve this error, use one of the following:</span></span>  
  
-   <span data-ttu-id="c1c75-138">Use una cuenta del mismo dominio que el usuario de Windows para el servicio de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1c75-138">Use an account from the same domain as the Windows user for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="c1c75-139">Si [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utiliza una cuenta de equipo, como servicio de red o sistema local, el equipo debe ser de confianza para el dominio que contiene el usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="c1c75-139">If [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is using a machine account such as Network Service or Local System, the machine must be trusted by the domain containing the Windows user.</span></span>  
  
-   <span data-ttu-id="c1c75-140">Use la autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1c75-140">Use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="c1c75-141">También puede ver el error 15517 al crear un procedimiento almacenado compilado de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="c1c75-141">You may also see error 15517 when creating a natively compiled stored procedure.</span></span> <span data-ttu-id="c1c75-142">Para obtener más información, vea [MSSQLSERVER_15517](../errors-events/mssqlserver-15517-database-engine-error.md).</span><span class="sxs-lookup"><span data-stu-id="c1c75-142">For more information, see [MSSQLSERVER_15517](../errors-events/mssqlserver-15517-database-engine-error.md).</span></span>  
  
## <a name="updating-a-natively-compiled-stored-procedure"></a><span data-ttu-id="c1c75-143">Actualizar un procedimiento almacenado compilado de forma nativa</span><span class="sxs-lookup"><span data-stu-id="c1c75-143">Updating a Natively Compiled Stored Procedure</span></span>  
 <span data-ttu-id="c1c75-144">No se permite la realización de operaciones de modificación en procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="c1c75-144">Performing alter operations on natively compiled stored procedures is not supported.</span></span> <span data-ttu-id="c1c75-145">Una manera de modificar un procedimiento almacenado compilado de forma nativa es quitar y volver a crear el procedimiento almacenado:</span><span class="sxs-lookup"><span data-stu-id="c1c75-145">One way to modify a natively compiled stored procedure is to drop and recreate the stored procedure:</span></span>  
  
1.  <span data-ttu-id="c1c75-146">Genere el script para los permisos en el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="c1c75-146">Generate script for the permissions on the stored procedure.</span></span>  
  
2.  <span data-ttu-id="c1c75-147">También puede generar el script para el procedimiento almacenado y guardarlo como copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c1c75-147">Optional, generate script for the stored procedure and save as a backup.</span></span>  
  
3.  <span data-ttu-id="c1c75-148">Quite el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="c1c75-148">Drop the stored procedure.</span></span>  
  
4.  <span data-ttu-id="c1c75-149">Cree el procedimiento almacenado con las modificaciones.</span><span class="sxs-lookup"><span data-stu-id="c1c75-149">Create the altered stored procedure.</span></span>  
  
5.  <span data-ttu-id="c1c75-150">Vuelva a aplicar los permisos del script al procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="c1c75-150">Re-apply the scripted permissions to the stored procedure.</span></span>  
  
 <span data-ttu-id="c1c75-151">El inconveniente de este procedimiento es que la aplicación estará sin conexión desde el inicio del paso 3 hasta la finalización del paso 5.</span><span class="sxs-lookup"><span data-stu-id="c1c75-151">The disadvantage to this procedure is the application will be offline from the start of step 3 through the completion of step 5.</span></span> <span data-ttu-id="c1c75-152">Esto puede tardar unos segundos y es posible que el cliente que utiliza la aplicación vea mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="c1c75-152">This may take a few seconds and the client using the application may see error messages.</span></span>  
  
 <span data-ttu-id="c1c75-153">Otra manera de modificar (eficazmente) un procedimiento almacenado compilado de forma nativa consiste en crear una nueva versión del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="c1c75-153">Another way to (effectively) modify a natively compiled stored procedure is to first create a new version of the stored procedure.</span></span> <span data-ttu-id="c1c75-154">Aquí, el procedimiento almacenado compilado de forma nativa tiene un número de versión asociado.</span><span class="sxs-lookup"><span data-stu-id="c1c75-154">Here, the natively compiled stored procedure has an associated version number.</span></span> <span data-ttu-id="c1c75-155">Llamaremos a la versión anterior SP_Vold y a la nueva versión SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="c1c75-155">We will call the old version SP_Vold and the new version SP_Vnew.</span></span>  
  
1.  <span data-ttu-id="c1c75-156">Genere el script para los permisos en SP_Vold.</span><span class="sxs-lookup"><span data-stu-id="c1c75-156">Generate script for the permissions on SP_Vold.</span></span>  
  
2.  <span data-ttu-id="c1c75-157">Cree SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="c1c75-157">Create SP_Vnew.</span></span>  
  
3.  <span data-ttu-id="c1c75-158">Aplique los permisos de SP_Vold a SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="c1c75-158">Apply the permissions of SP_Vold to SP_Vnew.</span></span>  
  
4.  <span data-ttu-id="c1c75-159">Actualice las referencias a SP_Vold para que señalen a SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="c1c75-159">Update references to SP_Vold to point to SP_Vnew.</span></span> <span data-ttu-id="c1c75-160">Esto puede llevarse a cabo de diferentes formas, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c1c75-160">This can be accomplished in different of ways, for example:</span></span>  
  
     <span data-ttu-id="c1c75-161">Utilice un procedimiento almacenado de contenedor (basado en disco), y modifíquelo para que señale a SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="c1c75-161">Use a wrapper (disk-based) stored procedure, and alter that procedure to point to SP_Vnew.</span></span> <span data-ttu-id="c1c75-162">El inconveniente de este método es el impacto sobre el rendimiento del direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="c1c75-162">The disadvantage of this approach is the performance impact of the indirection.</span></span>  
  
    ```sql  
    ALTER PROCEDURE dbo.SP p1,...,pn  
    AS  
      EXEC dbo.SP_Vnew p1,...,pn  
    GO  
    ```  
  
5.  <span data-ttu-id="c1c75-163">Si lo desea, quite SP_Vold.</span><span class="sxs-lookup"><span data-stu-id="c1c75-163">Optional, drop SP_Vold.</span></span>  
  
 <span data-ttu-id="c1c75-164">La ventaja de este método es que la aplicación no se queda sin conexión.</span><span class="sxs-lookup"><span data-stu-id="c1c75-164">The advantage of this approach is that the application does not go offline.</span></span> <span data-ttu-id="c1c75-165">Sin embargo, es necesario más trabajo para mantener las referencias y asegurarse de que siempre señalan a la última versión del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="c1c75-165">However, more work is required to maintain the references and make sure they always point to the latest version of the stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c75-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1c75-166">See Also</span></span>  
 [<span data-ttu-id="c1c75-167">Procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="c1c75-167">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
