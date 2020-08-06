---
title: Creación de un alias de tipo de datos definido por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.userdefineddatatype.general.f1
- sql12.swb.new.datatype.properties.general.f1
helpviewer_keywords:
- alias data types [SQL Server], creating
ms.assetid: b1dd8413-0cd0-411b-a79b-1bb043ccc62d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35db332c23e2df5a8e67c3677cd2411768816765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662088"
---
# <a name="create-a-user-defined-data-type-alias"></a><span data-ttu-id="54c45-102">Crear un alias de tipo de datos definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="54c45-102">Create a User-Defined Data Type Alias</span></span>
  <span data-ttu-id="54c45-103">En este tema se describe cómo crear un alias de tipo de datos definido por el usuario en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54c45-103">This topic describes how to create a new user-defined data type alias in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="54c45-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="54c45-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="54c45-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="54c45-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="54c45-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="54c45-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="54c45-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="54c45-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="54c45-108">**Para crear un alias de tipo de datos definido por el usuario, use:**</span><span class="sxs-lookup"><span data-stu-id="54c45-108">**To create a user-defined data type alias, using:**</span></span>  
  
     [<span data-ttu-id="54c45-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="54c45-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="54c45-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="54c45-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="54c45-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="54c45-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="54c45-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="54c45-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="54c45-113">El nombre de un alias de tipo de datos definido por el usuario alias debe cumplir las reglas de los identificadores.</span><span class="sxs-lookup"><span data-stu-id="54c45-113">The name of a user-defined data type alias must comply with the rules for identifiers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="54c45-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="54c45-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="54c45-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="54c45-115">Permissions</span></span>  
 <span data-ttu-id="54c45-116">Requiere el permiso CREATE TYPE en la base de datos actual y el permiso ALTER en *schema_name*.</span><span class="sxs-lookup"><span data-stu-id="54c45-116">Requires CREATE TYPE permission in the current database and ALTER permission on *schema_name*.</span></span> <span data-ttu-id="54c45-117">Si no se especifica *schema_name* , se aplican las reglas de resolución de nombres predeterminadas para determinar el esquema del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="54c45-117">If *schema_name* is not specified, the default name resolution rules for determining the schema for the current user apply.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="54c45-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="54c45-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-user-defined-data-type"></a><span data-ttu-id="54c45-119">Para crear un tipo de datos definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="54c45-119">To create a user-defined data type</span></span>  
  
1.  <span data-ttu-id="54c45-120">En el Explorador de objetos, expanda la opción **Bases de datos**, expanda una base de datos, expanda **Programación**y **Tipos**, haga clic con el botón derecho en **Tipos de datos definidos por el usuario**y haga clic en **Nuevo tipo de datos definido por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="54c45-120">In Object Explorer, expand **Databases**, expand a database, expand **Programmability**, expand **Types**, right-click **User-Defined Data Types**, and then click **New User-Defined Data Type**.</span></span>  
  
     <span data-ttu-id="54c45-121">**Permitir valores NULL**</span><span class="sxs-lookup"><span data-stu-id="54c45-121">**Allow NULLs**</span></span>  
     <span data-ttu-id="54c45-122">Especifique si el tipo de datos definido por el usuario puede aceptar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="54c45-122">Specify whether the user-defined data type can accept NULL values.</span></span> <span data-ttu-id="54c45-123">La capacidad de admitir valores NULL de un tipo de datos existente definido por el usuario no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="54c45-123">The nullability of an existing user-defined data type is not editable.</span></span>  
  
     <span data-ttu-id="54c45-124">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="54c45-124">**Data type**</span></span>  
     <span data-ttu-id="54c45-125">Seleccione el tipo de datos base en el cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="54c45-125">Select the base data type from the list box.</span></span> <span data-ttu-id="54c45-126">En el cuadro de lista se muestran todos los tipos de datos, excepto `geography`, `geometry`, `hierarchyid`, `sysname`, `timestamp` y `xml`.</span><span class="sxs-lookup"><span data-stu-id="54c45-126">The list box displays all data types except for the `geography`, `geometry`, `hierarchyid`, `sysname`, `timestamp` , and `xml` data types.</span></span> <span data-ttu-id="54c45-127">El tipo de un tipo de datos existente definido por el usuario no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="54c45-127">The data type of an existing user-defined data type is not editable.</span></span>  
  
     <span data-ttu-id="54c45-128">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="54c45-128">**Default**</span></span>  
     <span data-ttu-id="54c45-129">Opcionalmente, seleccione una regla o un valor predeterminado para enlazarlo al alias de tipo de datos definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="54c45-129">Optionally select a rule or a default to bind to the user-defined data type alias.</span></span>  
  
     <span data-ttu-id="54c45-130">**Longitud/Precisión**</span><span class="sxs-lookup"><span data-stu-id="54c45-130">**Length/Precision**</span></span>  
     <span data-ttu-id="54c45-131">Muestra la longitud o la precisión del tipo de datos, según proceda.</span><span class="sxs-lookup"><span data-stu-id="54c45-131">Displays the length or precision of the data type as applicable.</span></span> <span data-ttu-id="54c45-132">**Longitud** se aplica a los tipos de datos definidos por el usuario basados en personajes; **Precisión** solo se aplica a los tipos de datos numéricos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="54c45-132">**Length** applies to character-based user-defined data types; **Precision** applies only to numeric-based user-defined data types.</span></span> <span data-ttu-id="54c45-133">La etiqueta cambia en función del tipo de datos seleccionado con anterioridad.</span><span class="sxs-lookup"><span data-stu-id="54c45-133">The label changes depending on the data type selected earlier.</span></span> <span data-ttu-id="54c45-134">Este cuadro no puede modificarse si el tipo de datos seleccionado tiene una longitud o precisión fija.</span><span class="sxs-lookup"><span data-stu-id="54c45-134">This box is not editable if the length or precision of the selected data type is fixed.</span></span>  
  
     <span data-ttu-id="54c45-135">La longitud no se muestra para los tipos de datos `nvarchar(max)`, `varchar(max)` o `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="54c45-135">Length is not displayed for `nvarchar(max)`, `varchar(max)`, or `varbinary(max)` data types.</span></span>  
  
     <span data-ttu-id="54c45-136">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="54c45-136">**Name**</span></span>  
     <span data-ttu-id="54c45-137">Si va a crear un nuevo alias de tipo de datos definido por el usuario, escriba un nombre único que se usará en la base de datos para representar el tipo de datos definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="54c45-137">If you are creating a new user-defined data type alias, type a unique name to be used across the database to represent the user-defined data type.</span></span> <span data-ttu-id="54c45-138">El número máximo de caracteres debe coincidir con el tipo de datos del sistema `sysname` .</span><span class="sxs-lookup"><span data-stu-id="54c45-138">The maximum number of characters must match the system `sysname` data type.</span></span> <span data-ttu-id="54c45-139">El nombre de un alias existente de tipo de datos definido por el usuario no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="54c45-139">The name of an existing user-defined data type alias is not editable.</span></span>  
  
     <span data-ttu-id="54c45-140">**Regla**</span><span class="sxs-lookup"><span data-stu-id="54c45-140">**Rule**</span></span>  
     <span data-ttu-id="54c45-141">Opcionalmente, seleccione una regla para enlazarla al alias de tipo de datos definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="54c45-141">Optionally select a rule to bind to the user-defined data type alias.</span></span>  
  
     <span data-ttu-id="54c45-142">**Escala**</span><span class="sxs-lookup"><span data-stu-id="54c45-142">**Scale**</span></span>  
     <span data-ttu-id="54c45-143">Especifique el número máximo de dígitos decimales que se pueden almacenar a la derecha del separador decimal.</span><span class="sxs-lookup"><span data-stu-id="54c45-143">Specify the maximum number of decimal digits that can be stored to the right of the decimal point.</span></span>  
  
     <span data-ttu-id="54c45-144">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="54c45-144">**Schema**</span></span>  
     <span data-ttu-id="54c45-145">Seleccione un esquema de la lista de esquemas disponibles para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="54c45-145">Select a schema from a list of all schemas available to the current user.</span></span> <span data-ttu-id="54c45-146">La selección predeterminada es el esquema predeterminado del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="54c45-146">The default selection is the default schema for the current user.</span></span>  
  
     <span data-ttu-id="54c45-147">**Storage**</span><span class="sxs-lookup"><span data-stu-id="54c45-147">**Storage**</span></span>  
     <span data-ttu-id="54c45-148">Muestra el tamaño de almacenamiento máximo del alias de tipo de datos definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="54c45-148">Displays the maximum storage size for the user-defined data type alias.</span></span> <span data-ttu-id="54c45-149">El tamaño de almacenamiento máximo varía en función de la precisión.</span><span class="sxs-lookup"><span data-stu-id="54c45-149">Maximum storage sizes vary, based on precision.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="54c45-150">1 - 9</span><span class="sxs-lookup"><span data-stu-id="54c45-150">1 - 9</span></span>|<span data-ttu-id="54c45-151">5</span><span class="sxs-lookup"><span data-stu-id="54c45-151">5</span></span>|  
    |<span data-ttu-id="54c45-152">10 - 19</span><span class="sxs-lookup"><span data-stu-id="54c45-152">10 - 19</span></span>|<span data-ttu-id="54c45-153">9</span><span class="sxs-lookup"><span data-stu-id="54c45-153">9</span></span>|  
    |<span data-ttu-id="54c45-154">20 - 28</span><span class="sxs-lookup"><span data-stu-id="54c45-154">20 - 28</span></span>|<span data-ttu-id="54c45-155">13</span><span class="sxs-lookup"><span data-stu-id="54c45-155">13</span></span>|  
    |<span data-ttu-id="54c45-156">29 - 38</span><span class="sxs-lookup"><span data-stu-id="54c45-156">29 - 38</span></span>|<span data-ttu-id="54c45-157">17</span><span class="sxs-lookup"><span data-stu-id="54c45-157">17</span></span>|  
  
     <span data-ttu-id="54c45-158">`nchar` `nvarchar` En el caso de los tipos de datos y, el valor de almacenamiento siempre es dos veces el valor de **length**.</span><span class="sxs-lookup"><span data-stu-id="54c45-158">For `nchar` and `nvarchar` data types, the storage value is always two times the value in **Length**.</span></span>  
  
     <span data-ttu-id="54c45-159">El almacenamiento no se muestra para los tipos de datos `nvarchar(max)`, `varchar(max)` o `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="54c45-159">Storage is not displayed for `nvarchar(max)`, `varchar(max)`, or `varbinary(max)` data types.</span></span>  
  
2.  <span data-ttu-id="54c45-160">En el cuadro de diálogo **Nuevo tipo de datos definido por el usuario** , en el cuadro **Esquema** , escriba el esquema al que pertenecerá el alias de tipo de datos o use el botón Examinar para seleccionar el esquema.</span><span class="sxs-lookup"><span data-stu-id="54c45-160">In the **New User-defined Data Type** dialog box, in the **Schema** box, type the schema to own this data type alias, or use the browse button to select the schema.</span></span>  
  
3.  <span data-ttu-id="54c45-161">En el cuadro **Nombre** , escriba un nombre para el nuevo alias de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="54c45-161">In the **Name** box, type a name for the new data type alias.</span></span>  
  
4.  <span data-ttu-id="54c45-162">En el cuadro **Tipo de datos** , seleccione el tipo de datos en el que se basará el nuevo alias.</span><span class="sxs-lookup"><span data-stu-id="54c45-162">In the **Data type** box, select the data type that the new data type alias will be based on.</span></span>  
  
5.  <span data-ttu-id="54c45-163">Rellene los cuadros **Longitud**, **Precisión**y **Escala** si corresponde para el tipo de datos que esté creando.</span><span class="sxs-lookup"><span data-stu-id="54c45-163">Complete the **Length**, **Precision**, and **Scale** boxes if appropriate for that data type.</span></span>  
  
6.  <span data-ttu-id="54c45-164">Active la casilla **Permitir valores NULL** si el nuevo alias de tipo de datos puede permitir valores NULL.</span><span class="sxs-lookup"><span data-stu-id="54c45-164">Check **Allow NULLs** if the new data type alias can permit NULL values.</span></span>  
  
7.  <span data-ttu-id="54c45-165">En el área **Enlace** , rellene los cuadros **Predeterminado** o **Regla** si desea enlazar un valor predeterminado o una regla al nuevo alias de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="54c45-165">In the **Binding** area, complete the **Default** or **Rule** boxes if you want to bind a default or rule to the new data type alias.</span></span> <span data-ttu-id="54c45-166">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]no pueden crearse valores predeterminados ni reglas.</span><span class="sxs-lookup"><span data-stu-id="54c45-166">Defaults and rules cannot be created in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="54c45-167">Mediante [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54c45-167">Use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="54c45-168">El Explorador de plantillas incluye códigos de ejemplo para crear valores predeterminados y reglas.</span><span class="sxs-lookup"><span data-stu-id="54c45-168">Example code for creating defaults and rules are available in Template Explorer.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="54c45-169">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="54c45-169">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-user-defined-data-type-alias"></a><span data-ttu-id="54c45-170">Para crear un alias de tipo de datos definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="54c45-170">To create a user-defined data type alias</span></span>  
  
1.  <span data-ttu-id="54c45-171">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54c45-171">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="54c45-172">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="54c45-172">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="54c45-173">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="54c45-173">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="54c45-174">En este ejemplo siguiente se crea un alias de tipo de datos basado en el tipo de datos `varchar` suministrado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="54c45-174">This example creates a data type alias based on the system-supplied `varchar` data type.</span></span> <span data-ttu-id="54c45-175">El alias de tipo de datos `ssn` se usa para las columnas que almacenan números de la seguridad social de 11 cifras (999-99-9999).</span><span class="sxs-lookup"><span data-stu-id="54c45-175">The `ssn` data type alias is used for columns holding 11-digit social security numbers (999-99-9999).</span></span> <span data-ttu-id="54c45-176">La columna no puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="54c45-176">The column cannot be NULL.</span></span>  
  
```sql  
CREATE TYPE ssn  
FROM varchar(11) NOT NULL ;  
```  
  
## <a name="see-also"></a><span data-ttu-id="54c45-177">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54c45-177">See Also</span></span>  
 <span data-ttu-id="54c45-178">[Identificadores de base de datos](database-identifiers.md) </span><span class="sxs-lookup"><span data-stu-id="54c45-178">[Database Identifiers](database-identifiers.md) </span></span>  
 [<span data-ttu-id="54c45-179">CREATE TYPE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="54c45-179">CREATE TYPE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-type-transact-sql)  
  
  
