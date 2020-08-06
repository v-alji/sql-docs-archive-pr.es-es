---
title: Desencadenadores CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- inserted tables
- database objects [CLR integration], triggers
- common language runtime [SQL Server], triggers
- updated columns
- building database objects [CLR integration], triggers
- triggers [CLR integration]
- deleted tables
- EventData property
- SqlTriggerContext class
- transactions [CLR integration]
ms.assetid: 302a4e4a-3172-42b6-9cc0-4a971ab49c1c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 91f12b0d97d2e2065c5bb08d175253c22dffb032
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670532"
---
# <a name="clr-triggers"></a><span data-ttu-id="15fc9-102">Desencadenadores de CLR</span><span class="sxs-lookup"><span data-stu-id="15fc9-102">CLR Triggers</span></span>
  <span data-ttu-id="15fc9-103">Debido a la integración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Common Language Runtime (CLR), es posible usar cualquier lenguaje [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] para crear desencadenadores CLR.</span><span class="sxs-lookup"><span data-stu-id="15fc9-103">Because of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language runtime (CLR), you can use any [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] language to create CLR triggers.</span></span> <span data-ttu-id="15fc9-104">En esta sección se incluye información específica acerca de los desencadenadores implementados con la integración CLR.</span><span class="sxs-lookup"><span data-stu-id="15fc9-104">This section covers information specific to triggers implemented with CLR integration.</span></span> <span data-ttu-id="15fc9-105">Para obtener una descripción completa de los desencadenadores, vea [desencadenadores DDL](../../relational-databases/triggers/ddl-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="15fc9-105">For a complete discussion of triggers, see [DDL Triggers](../../relational-databases/triggers/ddl-triggers.md).</span></span>  
  
## <a name="what-are-triggers"></a><span data-ttu-id="15fc9-106">Qué son los desencadenadores</span><span class="sxs-lookup"><span data-stu-id="15fc9-106">What Are Triggers?</span></span>  
 <span data-ttu-id="15fc9-107">Un desencadenador es un tipo especial de procedimiento almacenado que se ejecuta automáticamente cuando se produce un evento de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="15fc9-107">A trigger is a special type of stored procedure that automatically runs when a language event executes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="15fc9-108">incluye dos tipos de desencadenadores: desencadenadores del lenguaje de manipulación de datos (DML) y desencadenadores del lenguaje de definición de datos (DDL).</span><span class="sxs-lookup"><span data-stu-id="15fc9-108">includes two general types of triggers: data manipulation language (DML) and data definition language (DDL) triggers.</span></span> <span data-ttu-id="15fc9-109">Los desencadenadores DML pueden usarse cuando las instrucciones `INSERT`, `UPDATE` o `DELETE` modifican los datos de una tabla o vista especificada.</span><span class="sxs-lookup"><span data-stu-id="15fc9-109">DML triggers can be used when `INSERT`, `UPDATE`, or `DELETE` statements modify data in a specified table or view.</span></span> <span data-ttu-id="15fc9-110">Los desencadenadores DDL activan procedimientos almacenados en respuesta a una serie de instrucciones DDL, principalmente instrucciones que comienzan por `CREATE`, `ALTER` y `DROP`.</span><span class="sxs-lookup"><span data-stu-id="15fc9-110">DDL triggers fire stored procedures in response to a variety of DDL statements, which are primarily statements that begin with `CREATE`, `ALTER`, and `DROP`.</span></span> <span data-ttu-id="15fc9-111">Los desencadenadores DDL pueden usarse en tareas administrativas, como la auditoría y regulación de operaciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="15fc9-111">DDL triggers can be used for administrative tasks, such as auditing and regulating database operations.</span></span>  
  
## <a name="unique-capabilities-of-clr-triggers"></a><span data-ttu-id="15fc9-112">Capacidades únicas de los desencadenadores CLR</span><span class="sxs-lookup"><span data-stu-id="15fc9-112">Unique Capabilities of CLR Triggers</span></span>  
 <span data-ttu-id="15fc9-113">Los desencadenadores escritos en [!INCLUDE[tsql](../../includes/tsql-md.md)] poseen la capacidad de determinar las columnas de la vista o de la tabla de activación que se han actualizado mediante el uso de las funciones `UPDATE(column)` y `COLUMNS_UPDATED()`.</span><span class="sxs-lookup"><span data-stu-id="15fc9-113">Triggers written in [!INCLUDE[tsql](../../includes/tsql-md.md)] have the capability of determining which columns from the firing view or table have been updated by using the `UPDATE(column)` and `COLUMNS_UPDATED()` functions.</span></span>  
  
 <span data-ttu-id="15fc9-114">Los desencadenadores escritos en lenguaje CLR se diferencian de otros objetos de integración CLR de varias formas significativas.</span><span class="sxs-lookup"><span data-stu-id="15fc9-114">Triggers written in a CLR language differ from other CLR integration objects in several significant ways.</span></span> <span data-ttu-id="15fc9-115">Los desencadenadores CLR pueden:</span><span class="sxs-lookup"><span data-stu-id="15fc9-115">CLR triggers can:</span></span>  
  
-   <span data-ttu-id="15fc9-116">Hacer referencia a datos de las tablas `INSERTED` y `DELETED`</span><span class="sxs-lookup"><span data-stu-id="15fc9-116">Reference data in the `INSERTED` and `DELETED` tables</span></span>  
  
-   <span data-ttu-id="15fc9-117">Determinar las columnas que se han modificado como resultado de una operación `UPDATE`</span><span class="sxs-lookup"><span data-stu-id="15fc9-117">Determine which columns have been modified as a result of an `UPDATE` operation</span></span>  
  
-   <span data-ttu-id="15fc9-118">Obtener acceso a información acerca de los objetos de base de datos afectados por la ejecución de instrucciones DDL.</span><span class="sxs-lookup"><span data-stu-id="15fc9-118">Access information about database objects affected by the execution of DDL statements.</span></span>  
  
 <span data-ttu-id="15fc9-119">Estas capacidades se proporcionan de forma inherente en el lenguaje de consulta o por medio de la clase `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="15fc9-119">These capabilities are provided inherently in the query language, or by the `SqlTriggerContext` class.</span></span> <span data-ttu-id="15fc9-120">Para obtener información sobre las ventajas de la integración CLR y la elección entre código administrado y [!INCLUDE[tsql](../../includes/tsql-md.md)] , consulte [información general sobre la integración CLR](../../relational-databases/clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="15fc9-120">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../../relational-databases/clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="using-the-sqltriggercontext-class"></a><span data-ttu-id="15fc9-121">Usar la clase SqlTriggerContext</span><span class="sxs-lookup"><span data-stu-id="15fc9-121">Using the SqlTriggerContext Class</span></span>  
 <span data-ttu-id="15fc9-122">La clase `SqlTriggerContext` no puede construirse públicamente y solo puede obtenerse mediante el acceso a la propiedad `SqlContext.TriggerContext` dentro del cuerpo de un desencadenador CLR.</span><span class="sxs-lookup"><span data-stu-id="15fc9-122">The `SqlTriggerContext` class cannot be publicly constructed and can only be obtained by accessing the `SqlContext.TriggerContext` property within the body of a CLR trigger.</span></span> <span data-ttu-id="15fc9-123">La clase `SqlTriggerContext` puede obtenerse a partir del contexto `SqlContext` activo mediante una llamada a la propiedad `SqlContext.TriggerContext`:</span><span class="sxs-lookup"><span data-stu-id="15fc9-123">The `SqlTriggerContext` class can be obtained from the active `SqlContext` by calling the `SqlContext.TriggerContext` property:</span></span>  
  
 `SqlTriggerContext myTriggerContext = SqlContext.TriggerContext;`  
  
 <span data-ttu-id="15fc9-124">La clase `SqlTriggerContext` proporciona información de contexto acerca del desencadenador.</span><span class="sxs-lookup"><span data-stu-id="15fc9-124">The `SqlTriggerContext` class provides context information about the trigger.</span></span> <span data-ttu-id="15fc9-125">Esta información contextual incluye el tipo de acción que provocó la activación del desencadenador, las columnas que se modificaron en una operación UPDATE y, en el caso de un desencadenador DDL, una estructura XML `EventData` que describe la operación de desencadenamiento.</span><span class="sxs-lookup"><span data-stu-id="15fc9-125">This contextual information includes the type of action that caused the trigger to fire, which columns were modified in an UPDATE operation, and, in the case of a DDL trigger, an XML `EventData` structure which describes the triggering operation.</span></span> <span data-ttu-id="15fc9-126">Para obtener más información, vea [EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15fc9-126">For more information, see [EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql).</span></span>  
  
### <a name="determining-the-trigger-action"></a><span data-ttu-id="15fc9-127">Determinar la acción del desencadenador</span><span class="sxs-lookup"><span data-stu-id="15fc9-127">Determining the Trigger Action</span></span>  
 <span data-ttu-id="15fc9-128">Una vez que ha obtenido un `SqlTriggerContext`, puede usarlo para determinar el tipo de acción que provocó que se activara el desencadenador.</span><span class="sxs-lookup"><span data-stu-id="15fc9-128">Once you have obtained a `SqlTriggerContext`, you can use it to determine the type of action that caused the trigger to fire.</span></span> <span data-ttu-id="15fc9-129">Esta información se encuentra disponible a través de la propiedad `TriggerAction` de la clase `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="15fc9-129">This information is available through the `TriggerAction` property of the `SqlTriggerContext` class.</span></span>  
  
 <span data-ttu-id="15fc9-130">En el caso de los desencadenadores DML, la propiedad `TriggerAction` puede tener uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="15fc9-130">For DML triggers, the `TriggerAction` property can be one of the following values:</span></span>  
  
-   <span data-ttu-id="15fc9-131">TriggerAction.Update (0x1)</span><span class="sxs-lookup"><span data-stu-id="15fc9-131">TriggerAction.Update (0x1)</span></span>  
  
-   <span data-ttu-id="15fc9-132">TriggerAction.Insert (0x2)</span><span class="sxs-lookup"><span data-stu-id="15fc9-132">TriggerAction.Insert (0x2)</span></span>  
  
-   <span data-ttu-id="15fc9-133">TriggerAction.Delete (0x3)</span><span class="sxs-lookup"><span data-stu-id="15fc9-133">TriggerAction.Delete(0x3)</span></span>  
  
-   <span data-ttu-id="15fc9-134">En el caso de los desencadenadores DDL, la lista de valores posibles de TriggerAction es bastante más larga.</span><span class="sxs-lookup"><span data-stu-id="15fc9-134">For DDL triggers, the list of possible TriggerAction values is considerably longer.</span></span> <span data-ttu-id="15fc9-135">Para obtener más información, vea el tema relativo a la enumeración TriggerAction en el SDK de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="15fc9-135">Please see "TriggerAction Enumeration" in the .NET Framework SDK for more information.</span></span>  
  
### <a name="using-the-inserted-and-deleted-tables"></a><span data-ttu-id="15fc9-136">Usar las tablas Inserted y Deleted</span><span class="sxs-lookup"><span data-stu-id="15fc9-136">Using the Inserted and Deleted Tables</span></span>  
 <span data-ttu-id="15fc9-137">En las instrucciones de desencadenadores DML se usan dos tablas especiales: la tabla **Inserted** y la tabla **Deleted** .</span><span class="sxs-lookup"><span data-stu-id="15fc9-137">Two special tables are used in DML trigger statements: the **inserted** table and the **deleted** table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="15fc9-138">crea y administra automáticamente ambas tablas.</span><span class="sxs-lookup"><span data-stu-id="15fc9-138">automatically creates and manages these tables.</span></span> <span data-ttu-id="15fc9-139">Puede usar estas tablas temporales para probar los efectos de determinadas modificaciones en los datos y para establecer condiciones para las acciones de los desencadenadores DML; sin embargo, no es posible modificar los datos de las tablas directamente.</span><span class="sxs-lookup"><span data-stu-id="15fc9-139">You can use these temporary tables to test the effects of certain data modifications and to set conditions for DML trigger actions; however, you cannot alter the data in the tables directly.</span></span>  
  
 <span data-ttu-id="15fc9-140">Los desencadenadores CLR pueden tener acceso a las tablas **Inserted** y **Deleted** a través del proveedor en proceso de CLR.</span><span class="sxs-lookup"><span data-stu-id="15fc9-140">CLR triggers can access the **inserted** and **deleted** tables through the CLR in-process provider.</span></span> <span data-ttu-id="15fc9-141">Para ello, se obtiene un objeto `SqlCommand` del objeto SqlContext.</span><span class="sxs-lookup"><span data-stu-id="15fc9-141">This is done by obtaining a `SqlCommand` object from the SqlContext object.</span></span> <span data-ttu-id="15fc9-142">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="15fc9-142">For example:</span></span>  
  
 <span data-ttu-id="15fc9-143">C#</span><span class="sxs-lookup"><span data-stu-id="15fc9-143">C#</span></span>  
  
```  
SqlConnection connection = new SqlConnection ("context connection = true");  
connection.Open();  
SqlCommand command = connection.CreateCommand();  
command.CommandText = "SELECT * from " + "inserted";  
```  
  
 <span data-ttu-id="15fc9-144">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15fc9-144">Visual Basic</span></span>  
  
```  
Dim connection As New SqlConnection("context connection=true")  
Dim command As SqlCommand  
connection.Open()  
command = connection.CreateCommand()  
command.CommandText = "SELECT * FROM " + "inserted"  
```  
  
### <a name="determining-updated-columns"></a><span data-ttu-id="15fc9-145">Determinar las columnas actualizadas</span><span class="sxs-lookup"><span data-stu-id="15fc9-145">Determining Updated Columns</span></span>  
 <span data-ttu-id="15fc9-146">Puede determinar el número de columnas que se han modificado en una operación UPDATE mediante el uso de la propiedad `ColumnCount` del objeto `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="15fc9-146">You can determine the number of columns that were modified by an UPDATE operation by using the `ColumnCount` property of the `SqlTriggerContext` object.</span></span> <span data-ttu-id="15fc9-147">Puede usar el método `IsUpdatedColumn`, que toma el ordinal de la columna como parámetro de entrada, para determinar si la columna se ha actualizado.</span><span class="sxs-lookup"><span data-stu-id="15fc9-147">You can use the `IsUpdatedColumn` method, which takes the column ordinal as an input parameter, to determine whether the column was updated.</span></span> <span data-ttu-id="15fc9-148">Un valor `True` indica que la columna se ha actualizado.</span><span class="sxs-lookup"><span data-stu-id="15fc9-148">A `True` value indicates that the column has been updated.</span></span>  
  
 <span data-ttu-id="15fc9-149">Por ejemplo, este fragmento de código (del desencadenador EmailAudit que se muestra más adelante en este tema) muestra todas las columnas actualizadas:</span><span class="sxs-lookup"><span data-stu-id="15fc9-149">For example, this code snippet (from the EmailAudit trigger later in this topic) lists all of the columns updated:</span></span>  
  
 <span data-ttu-id="15fc9-150">C#</span><span class="sxs-lookup"><span data-stu-id="15fc9-150">C#</span></span>  
  
```  
reader = command.ExecuteReader();  
reader.Read();  
for (int columnNumber = 0; columnNumber < triggContext.ColumnCount; columnNumber++)  
{  
   pipe.Send("Updated column "  
      + reader.GetName(columnNumber) + "? "  
   + triggContext.IsUpdatedColumn(columnNumber).ToString());  
 }  
  
 reader.Close();  
```  
  
 <span data-ttu-id="15fc9-151">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15fc9-151">Visual Basic</span></span>  
  
```  
reader = command.ExecuteReader()  
reader.Read()  
Dim columnNumber As Integer  
  
For columnNumber=0 To triggContext.ColumnCount-1  
  
   pipe.Send("Updated column " & reader.GetName(columnNumber) & _  
   "? " & triggContext.IsUpdatedColumn(columnNumber).ToString() )  
  
Next  
  
reader.Close()  
```  
  
### <a name="accessing-eventdata-for-clr-ddl-triggers"></a><span data-ttu-id="15fc9-152">Obtener acceso a EventData para desencadenadores DDL de CLR</span><span class="sxs-lookup"><span data-stu-id="15fc9-152">Accessing EventData for CLR DDL Triggers</span></span>  
 <span data-ttu-id="15fc9-153">Los desencadenadores DDL, al igual que los desencadenadores normales, activan procedimientos almacenados en respuesta a un evento.</span><span class="sxs-lookup"><span data-stu-id="15fc9-153">DDL triggers, like regular triggers, fire stored procedures in response to an event.</span></span> <span data-ttu-id="15fc9-154">Pero, a diferencia de los desencadenadores DML, no se activan en respuesta a instrucciones UPDATE, INSERT o DELETE en una tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="15fc9-154">But unlike DML triggers, they do not fire in response to UPDATE, INSERT, or DELETE statements on a table or view.</span></span> <span data-ttu-id="15fc9-155">En lugar de ello, se activan en respuesta a una serie de instrucciones DDL, principalmente instrucciones que comienzan por CREATE, ALTER y DROP.</span><span class="sxs-lookup"><span data-stu-id="15fc9-155">Instead, they fire in response to a variety of DDL statements, which are primarily statements that begin with CREATE, ALTER, and DROP.</span></span> <span data-ttu-id="15fc9-156">Los desencadenadores DDL pueden usarse en tareas administrativas, como la auditoría y supervisión de operaciones de base de datos y cambios de esquema.</span><span class="sxs-lookup"><span data-stu-id="15fc9-156">DDL triggers can be used for administrative tasks, such as auditing and monitoring of database operations and schema changes.</span></span>  
  
 <span data-ttu-id="15fc9-157">Encontrará información acerca de un evento que activa un desencadenador DDL en la propiedad `EventData` de la clase `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="15fc9-157">Information about an event that fires a DDL trigger is available in the `EventData` property of the `SqlTriggerContext` class.</span></span> <span data-ttu-id="15fc9-158">Esta propiedad contiene un valor `xml`.</span><span class="sxs-lookup"><span data-stu-id="15fc9-158">This property contains an `xml` value.</span></span> <span data-ttu-id="15fc9-159">El esquema XML incluye información acerca de:</span><span class="sxs-lookup"><span data-stu-id="15fc9-159">The xml schema includes information about:</span></span>  
  
-   <span data-ttu-id="15fc9-160">La hora del evento.</span><span class="sxs-lookup"><span data-stu-id="15fc9-160">The time of the event.</span></span>  
  
-   <span data-ttu-id="15fc9-161">El Id. de proceso del sistema (SPID) de la conexión durante la que se ha ejecutado el desencadenador.</span><span class="sxs-lookup"><span data-stu-id="15fc9-161">The System Process ID (SPID) of the connection during which the trigger executed.</span></span>  
  
-   <span data-ttu-id="15fc9-162">El tipo de evento que ha activado el desencadenador.</span><span class="sxs-lookup"><span data-stu-id="15fc9-162">The type of event that fired the trigger.</span></span>  
  
 <span data-ttu-id="15fc9-163">A continuación, en función del tipo de evento, el esquema incluirá información adicional, como la base de datos en la que se ha producido el evento, el objeto en el que se ha producido el evento y el comando [!INCLUDE[tsql](../../includes/tsql-md.md)] del evento.</span><span class="sxs-lookup"><span data-stu-id="15fc9-163">Then, depending on the event type, the schema includes additional information, such as the database in which the event occurred, the object against which the event occurred, and the [!INCLUDE[tsql](../../includes/tsql-md.md)] command of the event.</span></span>  
  
 <span data-ttu-id="15fc9-164">En el ejemplo que se muestra a continuación, el siguiente desencadenador DDL devuelve la propiedad `EventData` sin formato.</span><span class="sxs-lookup"><span data-stu-id="15fc9-164">In the following example, the following DDL trigger returns the raw `EventData` property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="15fc9-165">El envío de resultados y mensajes a través del objeto `SqlPipe` se muestra aquí únicamente como ejemplo y, en general, no se aconseja para el código de producción cuando se programan desencadenadores CLR.</span><span class="sxs-lookup"><span data-stu-id="15fc9-165">Sending results and messages through the `SqlPipe` object is shown here for illustrative purposes only and is generally discouraged for production code when programming CLR triggers.</span></span> <span data-ttu-id="15fc9-166">Otros datos devueltos pueden ser inesperados y conducir a errores en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="15fc9-166">Additional data returned may be unexpected and lead to application errors.</span></span>  
  
 <span data-ttu-id="15fc9-167">C#</span><span class="sxs-lookup"><span data-stu-id="15fc9-167">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Xml;  
using System.Text.RegularExpressions;  
  
public class CLRTriggers  
{  
   public static void DropTableTrigger()  
   {  
       SqlTriggerContext triggContext = SqlContext.TriggerContext;             
  
       switch(triggContext.TriggerAction)  
       {  
           case TriggerAction.DropTable:  
           SqlContext.Pipe.Send("Table dropped! Here's the EventData:");  
           SqlContext.Pipe.Send(triggContext.EventData.Value);  
           break;  
  
           default:  
           SqlContext.Pipe.Send("Something happened! Here's the EventData:");  
           SqlContext.Pipe.Send(triggContext.EventData.Value);  
           break;  
       }  
   }  
}  
```  
  
 <span data-ttu-id="15fc9-168">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15fc9-168">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class CLRTriggers   
  
    Public Shared Sub DropTableTrigger()  
        Dim triggContext As SqlTriggerContext  
        triggContext = SqlContext.TriggerContext  
  
        Select Case triggContext.TriggerAction  
           Case TriggerAction.DropTable  
              SqlContext.Pipe.Send("Table dropped! Here's the EventData:")  
              SqlContext.Pipe.Send(triggContext.EventData.Value)  
  
           Case Else  
              SqlContext.Pipe.Send("Something else happened! Here's the EventData:")  
              SqlContext.Pipe.Send(triggContext.EventData.Value)  
  
        End Select  
    End Sub  
End Class     
```  
  
 <span data-ttu-id="15fc9-169">El siguiente resultado de ejemplo es el valor de la propiedad `EventData` tras la activación de un desencadenador DDL por parte de un evento `CREATE TABLE`</span><span class="sxs-lookup"><span data-stu-id="15fc9-169">The following sample output is the `EventData` property value after a DDL trigger fired by a `CREATE TABLE` event:</span></span>  
  
 `<EVENT_INSTANCE><PostTime>2004-04-16T21:17:16.160</PostTime><SPID>58</SPID><EventType>CREATE_TABLE</EventType><ServerName>MACHINENAME</ServerName><LoginName>MYDOMAIN\myname</LoginName><UserName>MYDOMAIN\myname</UserName><DatabaseName>AdventureWorks</DatabaseName><SchemaName>dbo</SchemaName><ObjectName>UserName</ObjectName><ObjectType>TABLE</ObjectType><TSQLCommand><SetOptions ANSI_NULLS="ON" ANSI_NULL_DEFAULT="ON" ANSI_PADDING="ON" QUOTED_IDENTIFIER="ON" ENCRYPTED="FALSE" /><CommandText>create table dbo.UserName  
(  
 UserName varchar(50),  
 RealName varchar(50)  
)  
</CommandText></TSQLCommand></EVENT_INSTANCE>`  
  
 <span data-ttu-id="15fc9-170">Además de la información accesible a través de la clase `SqlTriggerContext`, las consultas pueden seguir haciendo referencia a `COLUMNS_UPDATED` y inserted/deleted dentro del texto de un comando que se ejecuta en proceso.</span><span class="sxs-lookup"><span data-stu-id="15fc9-170">In addition to the information accessible through the `SqlTriggerContext` class, queries can still refer to `COLUMNS_UPDATED` and inserted/deleted within the text of a command executed in-process.</span></span>  
  
## <a name="sample-clr-trigger"></a><span data-ttu-id="15fc9-171">Desencadenador CLR de ejemplo</span><span class="sxs-lookup"><span data-stu-id="15fc9-171">Sample CLR Trigger</span></span>  
 <span data-ttu-id="15fc9-172">Para este ejemplo, considere un escenario donde se permita que el usuario elija el identificador que desee, pero usted desea saber qué usuarios en concreto han especificado una dirección de correo electrónico como identificador.</span><span class="sxs-lookup"><span data-stu-id="15fc9-172">In this example, consider the scenario in which you let the user choose any ID they want, but you want to know the users that specifically entered an e-mail address as an ID.</span></span> <span data-ttu-id="15fc9-173">El siguiente desencadenador detectará esa información y la registrará en una tabla de auditoría.</span><span class="sxs-lookup"><span data-stu-id="15fc9-173">The following trigger would detect that information and log it to an audit table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="15fc9-174">El envío de resultados y mensajes a través del objeto `SqlPipe` se muestra aquí únicamente como ejemplo y, en general, no se aconseja para el código de producción.</span><span class="sxs-lookup"><span data-stu-id="15fc9-174">Sending results and messages through the `SqlPipe` object is shown here for illustrative purposes only and is generally discouraged for production code.</span></span> <span data-ttu-id="15fc9-175">Otros datos devueltos pueden ser inesperados y conducir a errores de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="15fc9-175">Additional data returned may be unexpected and lead to application errors</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Xml;  
using System.Text.RegularExpressions;  
  
public class CLRTriggers  
{  
   [SqlTrigger(Name = @"EmailAudit", Target = "[dbo].[Users]", Event = "FOR INSERT, UPDATE, DELETE")]  
   public static void EmailAudit()  
   {  
      string userName;  
      string realName;  
      SqlCommand command;  
      SqlTriggerContext triggContext = SqlContext.TriggerContext;  
      SqlPipe pipe = SqlContext.Pipe;  
      SqlDataReader reader;  
  
      switch (triggContext.TriggerAction)  
      {  
         case TriggerAction.Insert:  
         // Retrieve the connection that the trigger is using  
         using (SqlConnection connection  
            = new SqlConnection(@"context connection=true"))  
         {  
            connection.Open();  
            command = new SqlCommand(@"SELECT * FROM INSERTED;",  
               connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
            userName = (string)reader[0];  
            realName = (string)reader[1];  
            reader.Close();  
  
            if (IsValidEMailAddress(userName))  
            {  
               command = new SqlCommand(  
                  @"INSERT [dbo].[UserNameAudit] VALUES ('"  
                  + userName + @"', '" + realName + @"');",  
                  connection);  
               pipe.Send(command.CommandText);  
               command.ExecuteNonQuery();  
               pipe.Send("You inserted: " + userName);  
            }  
         }  
  
         break;  
  
         case TriggerAction.Update:  
         // Retrieve the connection that the trigger is using  
         using (SqlConnection connection  
            = new SqlConnection(@"context connection=true"))  
         {  
            connection.Open();  
            command = new SqlCommand(@"SELECT * FROM INSERTED;",  
               connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
  
            userName = (string)reader[0];  
            realName = (string)reader[1];  
  
            pipe.Send(@"You updated: '" + userName + @"' - '"  
               + realName + @"'");  
  
            for (int columnNumber = 0; columnNumber < triggContext.ColumnCount; columnNumber++)  
            {  
               pipe.Send("Updated column "  
                  + reader.GetName(columnNumber) + "? "  
                  + triggContext.IsUpdatedColumn(columnNumber).ToString());  
            }  
  
            reader.Close();  
         }  
  
         break;  
  
         case TriggerAction.Delete:  
            using (SqlConnection connection  
               = new SqlConnection(@"context connection=true"))  
               {  
                  connection.Open();  
                  command = new SqlCommand(@"SELECT * FROM DELETED;",  
                     connection);  
                  reader = command.ExecuteReader();  
  
                  if (reader.HasRows)  
                  {  
                     pipe.Send(@"You deleted the following rows:");  
                     while (reader.Read())  
                     {  
                        pipe.Send(@"'" + reader.GetString(0)  
                        + @"', '" + reader.GetString(1) + @"'");  
                     }  
  
                     reader.Close();  
  
                     //alternately, to just send a tabular resultset back:  
                     //pipe.ExecuteAndSend(command);  
                  }  
                  else  
                  {  
                     pipe.Send("No rows affected.");  
                  }  
               }  
  
               break;  
            }  
        }  
  
     public static bool IsValidEMailAddress(string email)  
     {  
         return Regex.IsMatch(email, @"^([\w-]+\.)*?[\w-]+@[\w-]+\.([\w-]+\.)*?[\w]+$");  
     }  
}  
```  
  
 <span data-ttu-id="15fc9-176">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15fc9-176">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
Imports System.Text.RegularExpressions  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class CLRTriggers   
  
    <SqlTrigger(Name:="EmailAudit", Target:="[dbo].[Users]", Event:="FOR INSERT, UPDATE, DELETE")> _  
    Public Shared Sub EmailAudit()  
        Dim userName As String  
        Dim realName As String  
        Dim command As SqlCommand  
        Dim triggContext As SqlTriggerContext  
        Dim pipe As SqlPipe  
        Dim reader As SqlDataReader    
  
        triggContext = SqlContext.TriggerContext      
        pipe = SqlContext.Pipe    
  
        Select Case triggContext.TriggerAction  
           Case TriggerAction.Insert  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM INSERTED;", connection)  
  
                 reader = command.ExecuteReader()  
                 reader.Read()  
  
                 userName = CType(reader(0), String)  
                 realName = CType(reader(1), String)  
  
                 reader.Close()  
  
                 If IsValidEmailAddress(userName) Then  
                     command = New SqlCommand("INSERT [dbo].[UserNameAudit] VALUES ('" & _  
                       userName & "', '" & realName & "');", connection)  
  
                    pipe.Send(command.CommandText)  
                    command.ExecuteNonQuery()  
                    pipe.Send("You inserted: " & userName)  
  
                 End If  
              End Using  
  
           Case TriggerAction.Update  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM INSERTED;", connection)  
  
                 reader = command.ExecuteReader()  
                 reader.Read()  
  
                 userName = CType(reader(0), String)  
                 realName = CType(reader(1), String)  
  
                 pipe.Send("You updated: " & userName & " - " & realName)  
  
                 Dim columnNumber As Integer  
  
                 For columnNumber=0 To triggContext.ColumnCount-1  
  
                    pipe.Send("Updated column " & reader.GetName(columnNumber) & _  
                      "? " & triggContext.IsUpdatedColumn(columnNumber).ToString() )  
  
                 Next  
  
                 reader.Close()  
              End Using  
  
           Case TriggerAction.Delete  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM DELETED;", connection)  
  
                 reader = command.ExecuteReader()  
  
                 If reader.HasRows Then  
                    pipe.Send("You deleted the following rows:")  
  
                    While reader.Read()  
  
                       pipe.Send( reader.GetString(0) & ", " & reader.GetString(1) )  
  
                    End While   
  
                    reader.Close()  
  
                    ' Alternately, just send a tabular resultset back:  
                    ' pipe.ExecuteAndSend(command)  
  
                 Else  
                   pipe.Send("No rows affected.")  
                 End If  
  
              End Using   
        End Select  
    End Sub  
  
    Public Shared Function IsValidEMailAddress(emailAddress As String) As Boolean  
  
       return Regex.IsMatch(emailAddress, "^([\w-]+\.)*?[\w-]+@[\w-]+\.([\w-]+\.)*?[\w]+$")  
    End Function      
End Class  
```  
  
 <span data-ttu-id="15fc9-177">Suponiendo que existen dos tablas con las siguientes definiciones:</span><span class="sxs-lookup"><span data-stu-id="15fc9-177">Assuming two tables exist with the following definitions:</span></span>  
  
```  
CREATE TABLE Users  
(  
    UserName nvarchar(200) NOT NULL,  
    RealName nvarchar(200) NOT NULL  
);  
GO CREATE TABLE UserNameAudit  
(  
    UserName nvarchar(200) NOT NULL,  
    RealName nvarchar(200) NOT NULL  
)  
```  
  
 <span data-ttu-id="15fc9-178">La [!INCLUDE[tsql](../../includes/tsql-md.md)] instrucción que crea el desencadenador en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es la siguiente y asume que el ensamblado **SQLCLRTest** ya está registrado en la base de datos actual [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15fc9-178">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that creates the trigger in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is as follows, and assumes assembly **SQLCLRTest** is already registered in the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
```  
CREATE TRIGGER EmailAudit  
ON Users  
FOR INSERT, UPDATE, DELETE  
AS  
EXTERNAL NAME SQLCLRTest.CLRTriggers.EmailAudit  
```  
  
## <a name="validating-and-canceling-invalid-transactions"></a><span data-ttu-id="15fc9-179">Validar y cancelar las transacciones no válidas</span><span class="sxs-lookup"><span data-stu-id="15fc9-179">Validating and Canceling Invalid Transactions</span></span>  
 <span data-ttu-id="15fc9-180">Es normal usar desencadenadores para validar y cancelar transacciones INSERT, UPDATE o DELETE no válidas o para impedir que se realicen cambios en el esquema de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="15fc9-180">Using triggers to validate and cancel invalid INSERT, UPDATE, or DELETE transactions or to prevent changes to your database schema is common.</span></span> <span data-ttu-id="15fc9-181">Esto puede realizarse incorporando una lógica de validación en el desencadenador y, a continuación, revirtiendo la transacción actual si la acción no cumple los criterios de validación.</span><span class="sxs-lookup"><span data-stu-id="15fc9-181">This can be accomplished by incorporating validation logic into your trigger and then rolling back the current transaction if the action does not meet the validation criteria.</span></span>  
  
 <span data-ttu-id="15fc9-182">Cuando se llama al método `Transaction.Rollback` o a un objeto SqlCommand con el texto de comando "TRANSACTION ROLLBACK" dentro de un desencadenador, se inicia una excepción con un mensaje de error ambiguo y debe incluirse dentro de un bloque try/catch.</span><span class="sxs-lookup"><span data-stu-id="15fc9-182">When called within a trigger, the `Transaction.Rollback` method or a SqlCommand with the command text "TRANSACTION ROLLBACK" throws an exception with an ambiguous error message and must be wrapped in a try/catch block.</span></span> <span data-ttu-id="15fc9-183">El mensaje de error que aparece es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="15fc9-183">The error message you see is similar to the following:</span></span>  
  
```  
Msg 6549, Level 16, State 1, Procedure trig_InsertValidator, Line 0  
A .NET Framework error occurred during execution of user defined routine or aggregate 'trig_InsertValidator':   
System.Data.SqlClient.SqlException: Transaction is not allowed to roll back inside a user defined routine, trigger or aggregate because the transaction is not started in that CLR level. Change application logic to enforce strict transaction nesting... User transaction, if any, will be rolled back.  
```  
  
 <span data-ttu-id="15fc9-184">Se espera esta excepción y el bloque try/catch resulta necesario para que continúe la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="15fc9-184">This exception is expected and the try/catch block is necessary for code execution to continue.</span></span> <span data-ttu-id="15fc9-185">Cuando finaliza la ejecución del código del desencadenador, se inicia otra excepción:</span><span class="sxs-lookup"><span data-stu-id="15fc9-185">When the trigger code finishes execution, another exception is raised</span></span>  
  
```  
Msg 3991, Level 16, State 1, Procedure trig_InsertValidator, Line 1   
The context transaction which was active before entering user defined routine, trigger or aggregate "trig_InsertValidator" has been ended inside of it, which is not allowed. Change application logic to enforce strict transaction nesting.  
The statement has been terminated.  
```  
  
 <span data-ttu-id="15fc9-186">También se espera esta excepción y es necesario incluir un bloque try/catch alrededor de la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] que realiza la acción que activa el desencadenador para que la ejecución pueda continuar.</span><span class="sxs-lookup"><span data-stu-id="15fc9-186">This exception is also expected, and a try/catch block around the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that performs the action that fires the trigger is necessary so that execution can continue.</span></span> <span data-ttu-id="15fc9-187">A pesar de las dos excepciones iniciadas, la transacción se revierte y no se confirman los cambios en la tabla.</span><span class="sxs-lookup"><span data-stu-id="15fc9-187">Despite the two exceptions thrown, the transaction is rolled back and the changes are not committed to the table.</span></span> <span data-ttu-id="15fc9-188">Una diferencia importante entre los desencadenadores CLR y los desencadenadores [!INCLUDE[tsql](../../includes/tsql-md.md)] es que los desencadenadores [!INCLUDE[tsql](../../includes/tsql-md.md)] pueden seguir realizando más trabajo una vez que se ha revertido la transacción.</span><span class="sxs-lookup"><span data-stu-id="15fc9-188">A major difference between CLR triggers and [!INCLUDE[tsql](../../includes/tsql-md.md)] triggers is that [!INCLUDE[tsql](../../includes/tsql-md.md)] triggers can continue to perform more work after the transaction is rolled back.</span></span>  
  
### <a name="example"></a><span data-ttu-id="15fc9-189">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15fc9-189">Example</span></span>  
 <span data-ttu-id="15fc9-190">El desencadenador siguiente realiza una validación simple de instrucciones INSERT en una tabla.</span><span class="sxs-lookup"><span data-stu-id="15fc9-190">The following trigger performs simple validation of INSERT statements on a table.</span></span> <span data-ttu-id="15fc9-191">Si el valor entero insertado es igual a uno, la transacción se revierte y el valor no se inserta en la tabla.</span><span class="sxs-lookup"><span data-stu-id="15fc9-191">If the inserted integer value is equal to one, the transaction is rolled back and the value is not inserted into the table.</span></span> <span data-ttu-id="15fc9-192">El resto de los valores enteros se insertan en la tabla.</span><span class="sxs-lookup"><span data-stu-id="15fc9-192">All other integer values are inserted into the table.</span></span> <span data-ttu-id="15fc9-193">Tenga en cuenta el bloque try/catch alrededor del método `Transaction.Rollback`.</span><span class="sxs-lookup"><span data-stu-id="15fc9-193">Note the try/catch block around the `Transaction.Rollback` method.</span></span> <span data-ttu-id="15fc9-194">El script [!INCLUDE[tsql](../../includes/tsql-md.md)] crea una tabla de prueba, un ensamblado y un procedimiento almacenado administrado.</span><span class="sxs-lookup"><span data-stu-id="15fc9-194">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script creates a test table, assembly, and managed stored procedure.</span></span> <span data-ttu-id="15fc9-195">Tenga en cuenta que las dos instrucciones INSERT se incluyen en un bloque try/catch, de modo que la excepción iniciada se detecta al finalizar la ejecución del desencadenador.</span><span class="sxs-lookup"><span data-stu-id="15fc9-195">Note that the two INSERT statements are wrapped in a try/catch block so that the exception thrown when the trigger finishes execution is caught.</span></span>  
  
 <span data-ttu-id="15fc9-196">C#</span><span class="sxs-lookup"><span data-stu-id="15fc9-196">C#</span></span>  
  
```  
using System;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;  
using System.Transactions;  
  
public partial class Triggers  
{  
    // Enter existing table or view for the target and uncomment the attribute line  
    // [Microsoft.SqlServer.Server.SqlTrigger (Name="trig_InsertValidator", Target="Table1", Event="FOR INSERT")]  
    public static void trig_InsertValidator()  
    {  
        using (SqlConnection connection = new SqlConnection(@"context connection=true"))  
        {  
            SqlCommand command;  
            SqlDataReader reader;  
            int value;  
  
            // Open the connection.  
            connection.Open();  
  
            // Get the inserted value.  
            command = new SqlCommand(@"SELECT * FROM INSERTED", connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
            value = (int)reader[0];  
            reader.Close();  
  
            // Rollback the transaction if a value of 1 was inserted.  
            if (1 == value)  
            {  
                try  
                {  
                    // Get the current transaction and roll it back.  
                    Transaction trans = Transaction.Current;  
                    trans.Rollback();                      
                }  
                catch (SqlException ex)  
                {  
                    // Catch the expected exception.                      
                }  
            }  
            else  
            {  
                // Perform other actions here.  
            }  
  
            // Close the connection.  
            connection.Close();              
        }  
    }  
}  
```  
  
 <span data-ttu-id="15fc9-197">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15fc9-197">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Transactions  
  
Partial Public Class Triggers  
' Enter existing table or view for the target and uncomment the attribute line  
' <Microsoft.SqlServer.Server.SqlTrigger(Name:="trig_InsertValidator", Target:="Table1", Event:="FOR INSERT")> _  
Public Shared Sub  trig_InsertValidator ()  
    Using connection As New SqlConnection("context connection=true")  
  
        Dim command As SqlCommand  
        Dim reader As SqlDataReader  
        Dim value As Integer  
  
        ' Open the connection.  
        connection.Open()  
  
        ' Get the inserted value.  
        command = New SqlCommand("SELECT * FROM INSERTED", connection)  
        reader = command.ExecuteReader()  
        reader.Read()  
        value = CType(reader(0), Integer)  
        reader.Close()  
  
        ' Rollback the transaction if a value of 1 was inserted.  
        If value = 1 Then  
  
            Try  
                ' Get the current transaction and roll it back.  
                Dim trans As Transaction  
                trans = Transaction.Current  
                trans.Rollback()  
  
            Catch ex As SqlException  
  
                ' Catch the exception.                      
            End Try  
        Else  
  
            ' Perform other actions here.  
        End If  
  
        ' Close the connection.  
        connection.Close()  
    End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="15fc9-198">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="15fc9-198">Transact-SQL</span></span>  
  
```  
-- Create the test table, assembly, and trigger.  
CREATE TABLE Table1(c1 int);  
go  
  
CREATE ASSEMBLY ValidationTriggers from 'E:\programming\ ValidationTriggers.dll';  
go  
  
CREATE TRIGGER trig_InsertValidator  
ON Table1  
FOR INSERT  
AS EXTERNAL NAME ValidationTriggers.Triggers.trig_InsertValidator;  
go  
  
-- Use a Try/Catch block to catch the expected exception  
BEGIN TRY  
   INSERT INTO Table1 VALUES(42)  
   INSERT INTO Table1 VALUES(1)  
END TRY  
BEGIN CATCH  
  SELECT ERROR_NUMBER() AS ErrorNum, ERROR_MESSAGE() AS ErrorMessage  
END CATCH;  
  
-- Clean up.  
DROP TRIGGER trig_InsertValidator;  
DROP ASSEMBLY ValidationTriggers;  
DROP TABLE Table1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="15fc9-199">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15fc9-199">See Also</span></span>  
 <span data-ttu-id="15fc9-200">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="15fc9-200">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="15fc9-201">[Desencadenadores DML](../../relational-databases/triggers/dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="15fc9-201">[DML Triggers](../../relational-databases/triggers/dml-triggers.md) </span></span>  
 <span data-ttu-id="15fc9-202">[Desencadenadores DDL](../../relational-databases/triggers/ddl-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="15fc9-202">[DDL Triggers](../../relational-databases/triggers/ddl-triggers.md) </span></span>  
 <span data-ttu-id="15fc9-203">[TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="15fc9-203">[TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql) </span></span>  
 <span data-ttu-id="15fc9-204">[Crear objetos de base de datos con Common Language Runtime &#40;CLR&#41; Integration](../../relational-databases/clr-integration/database-objects/building-database-objects-with-common-language-runtime-clr-integration.md) </span><span class="sxs-lookup"><span data-stu-id="15fc9-204">[Building Database Objects with Common Language Runtime &#40;CLR&#41; Integration](../../relational-databases/clr-integration/database-objects/building-database-objects-with-common-language-runtime-clr-integration.md) </span></span>  
 [<span data-ttu-id="15fc9-205">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="15fc9-205">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
