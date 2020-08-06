---
title: Descripción de errores del motor de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server], about errors
- errors [SQL Server], Database Engine
- errors [SQL Server]
- Database Engine [SQL Server], errors
ms.assetid: ddaca9d3-956f-46a5-8cd3-a7a15ec75878
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: aa8747066433488a8517d2931ad51f082075a66f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673686"
---
# <a name="understanding-database-engine-errors"></a><span data-ttu-id="9d94e-102">Descripción de errores del motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="9d94e-102">Understanding Database Engine Errors</span></span>
  <span data-ttu-id="9d94e-103">Los errores producidos por [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] tienen los atributos descritos en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9d94e-103">Errors raised by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] have the attributes described in the following table.</span></span>  
  
|<span data-ttu-id="9d94e-104">Atributo</span><span class="sxs-lookup"><span data-stu-id="9d94e-104">Attribute</span></span>|<span data-ttu-id="9d94e-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d94e-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d94e-106">Número de error</span><span class="sxs-lookup"><span data-stu-id="9d94e-106">Error number</span></span>|<span data-ttu-id="9d94e-107">Cada mensaje de error tiene un número de error único.</span><span class="sxs-lookup"><span data-stu-id="9d94e-107">Each error message has a unique error number.</span></span>|  
|<span data-ttu-id="9d94e-108">Cadena de mensaje de error</span><span class="sxs-lookup"><span data-stu-id="9d94e-108">Error message string</span></span>|<span data-ttu-id="9d94e-109">El mensaje de error contiene información de diagnóstico acerca de la causa del error.</span><span class="sxs-lookup"><span data-stu-id="9d94e-109">The error message contains diagnostic information about the cause of the error.</span></span> <span data-ttu-id="9d94e-110">Muchos mensajes de error tienen variables de sustitución en las que se inserta información como, por ejemplo, el nombre del objeto que genera el error.</span><span class="sxs-lookup"><span data-stu-id="9d94e-110">Many error messages have substitution variables in which information, such as the name of the object generating the error, is inserted.</span></span>|  
|<span data-ttu-id="9d94e-111">severity</span><span class="sxs-lookup"><span data-stu-id="9d94e-111">Severity</span></span>|<span data-ttu-id="9d94e-112">La gravedad indica la importancia del error.</span><span class="sxs-lookup"><span data-stu-id="9d94e-112">The severity indicates how serious the error is.</span></span> <span data-ttu-id="9d94e-113">Los errores que tienen una gravedad baja, como 1 o 2, son mensajes informativos o advertencias de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="9d94e-113">Errors that have a low severity, such as 1 or 2, are information messages or low-level warnings.</span></span> <span data-ttu-id="9d94e-114">Los errores que tienen una gravedad alta indican problemas que deben ser atendidos tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="9d94e-114">Errors that have a high severity indicate problems that should be addressed as soon as possible.</span></span> <span data-ttu-id="9d94e-115">Para obtener más información sobre los niveles de gravedad, vea [Niveles de gravedad de error del motor de base de datos](database-engine-error-severities.md).</span><span class="sxs-lookup"><span data-stu-id="9d94e-115">For more information about severities, see [Database Engine Error Severities](database-engine-error-severities.md).</span></span>|  
|<span data-ttu-id="9d94e-116">State</span><span class="sxs-lookup"><span data-stu-id="9d94e-116">State</span></span>|<span data-ttu-id="9d94e-117">Algunos mensajes de error se pueden generar en varios puntos del código de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d94e-117">Some error messages can be raised at multiple points in the code for the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="9d94e-118">Por ejemplo, el error 1105 se puede generar bajo diferentes condiciones.</span><span class="sxs-lookup"><span data-stu-id="9d94e-118">For example, an 1105 error can be raised for several different conditions.</span></span> <span data-ttu-id="9d94e-119">Cada condición específica bajo la que se genera un error asigna un código de estado único.</span><span class="sxs-lookup"><span data-stu-id="9d94e-119">Each specific condition that raises an error assigns a unique state code.</span></span><br /><br /> <span data-ttu-id="9d94e-120">Cuando vea bases de datos que contengan información sobre problemas conocidos como, por ejemplo, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base, puede utilizar el número de estado para determinar si el problema registrado es el mismo que el error con el que se ha encontrado.</span><span class="sxs-lookup"><span data-stu-id="9d94e-120">When you are viewing databases that contain information about known issues, such as the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base, you can use the state number to determine whether the recorded issue is the same as the error you have encountered.</span></span> <span data-ttu-id="9d94e-121">Por ejemplo, si un artículo de Knowledge Base describe un error 1105 que tiene un estado 2 y el mensaje de error 1105 que ha recibido tenía un estado 3, el error tendrá probablemente una causa diferente a la explicada en el artículo.</span><span class="sxs-lookup"><span data-stu-id="9d94e-121">For example, if a Knowledge Base Article describes an 1105 error that has a state of 2 and the 1105 error message you received had a state of 3, the error probably has a different cause than the one reported in the article.</span></span><br /><br /> <span data-ttu-id="9d94e-122">Un ingeniero de soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] también puede utilizar el código de estado de un error para localizar la ubicación del código fuente donde se ha generado el código de error.</span><span class="sxs-lookup"><span data-stu-id="9d94e-122">A [!INCLUDE[msCoName](../../includes/msconame-md.md)] support engineer can also use the state code from an error to find the location in the source code where that error code is being raised.</span></span> <span data-ttu-id="9d94e-123">Esta información puede proporcionar ideas adicionales sobre cómo diagnosticar el problema.</span><span class="sxs-lookup"><span data-stu-id="9d94e-123">This information might provide additional ideas on how to diagnose the problem.</span></span>|  
|<span data-ttu-id="9d94e-124">Nombre del procedimiento</span><span class="sxs-lookup"><span data-stu-id="9d94e-124">Procedure name</span></span>|<span data-ttu-id="9d94e-125">Nombre del procedimiento almacenado o desencadenador en que se ha producido el error.</span><span class="sxs-lookup"><span data-stu-id="9d94e-125">Is the name of the stored procedure or trigger in which the error has occurred.</span></span>|  
|<span data-ttu-id="9d94e-126">Número de línea</span><span class="sxs-lookup"><span data-stu-id="9d94e-126">Line number</span></span>|<span data-ttu-id="9d94e-127">Indica qué instrucción de un lote, procedimiento almacenado, desencadenador o función ha generado el error.</span><span class="sxs-lookup"><span data-stu-id="9d94e-127">Indicates which statement in a batch, stored procedure, trigger, or function generated the error.</span></span>|  
  
 <span data-ttu-id="9d94e-128">Todos los mensajes de error (del sistema o definidos por el usuario) de una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] se encuentran en la vista de catálogo **sys.messages** .</span><span class="sxs-lookup"><span data-stu-id="9d94e-128">All system and user-defined error messages in an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] are contained in the **sys.messages** catalog view.</span></span> <span data-ttu-id="9d94e-129">Puede utilizar la instrucción RAISERROR para devolver a una aplicación errores definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="9d94e-129">You can use the RAISERROR statement to return user-defined errors to an application.</span></span>  
  
 <span data-ttu-id="9d94e-130">Todas las API de base de datos, como el espacio de nombres **SQLClient** de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], Objetos de datos ActiveX (ADO), OLE DB y conectividad abierta de bases de datos (ODBC), notifican los atributos de error básicos.</span><span class="sxs-lookup"><span data-stu-id="9d94e-130">All database APIs, such as the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] **SQLClient** namespace, ActiveX Data Objects (ADO), OLE DB, and Open Database Connectivity (ODBC), report the basic error attributes.</span></span> <span data-ttu-id="9d94e-131">Esta información incluye el número de error y la cadena del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9d94e-131">This information includes the error number and message string.</span></span> <span data-ttu-id="9d94e-132">No obstante, no todas las API informan de los demás atributos de error.</span><span class="sxs-lookup"><span data-stu-id="9d94e-132">However, not all the APIs report all the other error attributes.</span></span>  
  
 <span data-ttu-id="9d94e-133">La información sobre un error que se produce en el ámbito del bloque TRY de una construcción TRY...CATCH se puede obtener en código [!INCLUDE[tsql](../../includes/tsql-md.md)] mediante funciones como ERROR_LINE, ERROR_MESSAGE, ERROR_NUMBER, ERROR_PROCEDURE, ERROR_SEVERITY y ERROR_STATE en el ámbito del bloque CATCH asociado.</span><span class="sxs-lookup"><span data-stu-id="9d94e-133">Information about an error that occurs in the scope of the TRY block of a TRY...CATCH construct can be obtained in [!INCLUDE[tsql](../../includes/tsql-md.md)] code by using functions such as ERROR_LINE, ERROR_MESSAGE, ERROR_NUMBER, ERROR_PROCEDURE, ERROR_SEVERITY, and ERROR_STATE in the scope of the associated CATCH block.</span></span> <span data-ttu-id="9d94e-134">Para obtener más información, vea [TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9d94e-134">For more information, see [TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9d94e-135">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9d94e-135">Examples</span></span>  
 <span data-ttu-id="9d94e-136">En el siguiente ejemplo se envía una consulta a la vista de catálogo `sys.messages` en la que se solicita que devuelva una lista de todos los mensajes de error del sistema y definidos por el usuario en [!INCLUDE[ssDE](../../includes/ssde-md.md)] que tengan texto en inglés (`1033`).</span><span class="sxs-lookup"><span data-stu-id="9d94e-136">The following example queries the `sys.messages` catalog view to return a list of all system and user-defined error messages in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that have English text (`1033`).</span></span>  
  
```  
SELECT  
    message_id,  
    language_id,  
    severity,  
    is_event_logged,  
    text  
  FROM sys.messages  
  WHERE language_id = 1033;  
```  
  
 <span data-ttu-id="9d94e-137">Para obtener más información, vea [sys.messages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages).</span><span class="sxs-lookup"><span data-stu-id="9d94e-137">For more information, see [sys.messages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d94e-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d94e-138">See Also</span></span>  
 <span data-ttu-id="9d94e-139">[sys.messages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages) </span><span class="sxs-lookup"><span data-stu-id="9d94e-139">[sys.messages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages) </span></span>  
 <span data-ttu-id="9d94e-140">[RAISERROR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/raiserror-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d94e-140">[RAISERROR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/raiserror-transact-sql) </span></span>  
 <span data-ttu-id="9d94e-141">[@@ERROR &#40;Transact-SQL&#41;](/sql/t-sql/functions/error-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d94e-141">[@@ERROR &#40;Transact-SQL&#41;](/sql/t-sql/functions/error-transact-sql) </span></span>  
 <span data-ttu-id="9d94e-142">[TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d94e-142">[TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql) </span></span>  
 <span data-ttu-id="9d94e-143">[ERROR_LINE &#40;Transact-SQL&#41;](/sql/t-sql/functions/error-line-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d94e-143">[ERROR_LINE &#40;Transact-SQL&#41;](/sql/t-sql/functions/error-line-transact-sql) </span></span>  
 <span data-ttu-id="9d94e-144">[ERROR_MESSAGE &#40;Transact-SQL&#41;](/sql/t-sql/functions/error-message-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d94e-144">[ERROR_MESSAGE &#40;Transact-SQL&#41;](/sql/t-sql/functions/error-message-transact-sql) </span></span>  
 <span data-ttu-id="9d94e-145">[ERROR_NUMBER &#40;Transact-SQL&#41;](/sql/t-sql/functions/error-number-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d94e-145">[ERROR_NUMBER &#40;Transact-SQL&#41;](/sql/t-sql/functions/error-number-transact-sql) </span></span>  
 <span data-ttu-id="9d94e-146">[ERROR_PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/functions/error-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d94e-146">[ERROR_PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/functions/error-procedure-transact-sql) </span></span>  
 <span data-ttu-id="9d94e-147">[ERROR_SEVERITY &#40;Transact-SQL&#41;](/sql/t-sql/functions/error-severity-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d94e-147">[ERROR_SEVERITY &#40;Transact-SQL&#41;](/sql/t-sql/functions/error-severity-transact-sql) </span></span>  
 [<span data-ttu-id="9d94e-148">ERROR_STATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d94e-148">ERROR_STATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/error-state-transact-sql)  
  
  