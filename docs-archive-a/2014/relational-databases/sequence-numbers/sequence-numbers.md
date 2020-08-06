---
title: Números de secuencia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- sequence number object, overview
- sequence [Database Engine]
- autonumbers, sequences
- sequence numbers [SQL Server]
- sequence number object
ms.assetid: c900e30d-2fd3-4d5f-98ee-7832f37e79d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6c65b4df915a85cf0ec7c7c0c8c0ff9f6607ad96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750585"
---
# <a name="sequence-numbers"></a><span data-ttu-id="dfee7-102">Números de secuencia</span><span class="sxs-lookup"><span data-stu-id="dfee7-102">Sequence Numbers</span></span>
  <span data-ttu-id="dfee7-103">Una secuencia es un objeto enlazado a un esquema definido por el usuario que genera una secuencia de valores numéricos según la especificación con la que se creó la secuencia.</span><span class="sxs-lookup"><span data-stu-id="dfee7-103">A sequence is a user-defined schema-bound object that generates a sequence of numeric values according to the specification with which the sequence was created.</span></span> <span data-ttu-id="dfee7-104">La secuencia de valores numéricos se genera en orden ascendente o descendente en un intervalo definido y puede repetirse cuando se solicite.</span><span class="sxs-lookup"><span data-stu-id="dfee7-104">The sequence of numeric values is generated in an ascending or descending order at a defined interval and may cycle (repeat) as requested.</span></span> <span data-ttu-id="dfee7-105">Las secuencias, a diferencia de las columnas de identidad, no se asocian a tablas.</span><span class="sxs-lookup"><span data-stu-id="dfee7-105">Sequences, unlike identity columns, are not associated with tables.</span></span> <span data-ttu-id="dfee7-106">Una aplicación hace referencia a un objeto de secuencia para recibir su valor siguiente.</span><span class="sxs-lookup"><span data-stu-id="dfee7-106">An application refers to a sequence object to receive its next value.</span></span> <span data-ttu-id="dfee7-107">La aplicación controla la relación entre las secuencias y tablas.</span><span class="sxs-lookup"><span data-stu-id="dfee7-107">The relationship between sequences and tables is controlled by the application.</span></span> <span data-ttu-id="dfee7-108">Las aplicaciones de usuario pueden hacer referencia a un objeto de secuencia y coordinar las claves de valores entre varias filas y tablas.</span><span class="sxs-lookup"><span data-stu-id="dfee7-108">User applications can reference a sequence object and coordinate the values keys across multiple rows and tables.</span></span>  
  
 <span data-ttu-id="dfee7-109">Una secuencia se crea independientemente de las tablas utilizando la instrucción **CREATE SEQUENCE** .</span><span class="sxs-lookup"><span data-stu-id="dfee7-109">A sequence is created independently of the tables by using the **CREATE SEQUENCE** statement.</span></span> <span data-ttu-id="dfee7-110">Las opciones permiten controlar el incremento, los valores máximo y mínimo, el punto de inicio, la capacidad de reinicio automático y el almacenamiento en caché para aumentar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="dfee7-110">Options enable you to control the increment, maximum and minimum values, starting point, automatic restarting capability, and caching to improve performance.</span></span> <span data-ttu-id="dfee7-111">Para obtener información acerca de las opciones, vea [CREATE SEQUENCE](/sql/t-sql/statements/create-sequence-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfee7-111">For information about the options, see [CREATE SEQUENCE](/sql/t-sql/statements/create-sequence-transact-sql).</span></span>  
  
 <span data-ttu-id="dfee7-112">A diferencia de los valores de columnas de identidad que se generan cuando se insertan filas, una aplicación puede obtener el número de secuencia siguiente sin insertar la fila llamando a la función [NEXT VALUE FOR](/sql/t-sql/functions/next-value-for-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="dfee7-112">Unlike identity column values, which are generated when rows are inserted, an application can obtain the next sequence number before inserting the row by calling the [NEXT VALUE FOR](/sql/t-sql/functions/next-value-for-transact-sql) function.</span></span> <span data-ttu-id="dfee7-113">Se asigna el número de secuencia cuando se llama a NEXT VALUE FOR aun cuando el número nunca se inserta en una tabla.</span><span class="sxs-lookup"><span data-stu-id="dfee7-113">The sequence number is allocated when NEXT VALUE FOR is called even if the number is never inserted into a table.</span></span> <span data-ttu-id="dfee7-114">La función NEXT VALUE FOR se puede utilizar como valor predeterminado para una columna en una definición de tabla.</span><span class="sxs-lookup"><span data-stu-id="dfee7-114">The NEXT VALUE FOR function can be used as the default value for a column in a table definition.</span></span> <span data-ttu-id="dfee7-115">Use [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) para obtener un rango de varios números de secuencia de una sola vez.</span><span class="sxs-lookup"><span data-stu-id="dfee7-115">Use [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) to get a range of multiple sequence numbers at once.</span></span>  
  
 <span data-ttu-id="dfee7-116">Una secuencia se puede definir como cualquier tipo de datos enteros.</span><span class="sxs-lookup"><span data-stu-id="dfee7-116">A sequence can be defined as any integer data type.</span></span> <span data-ttu-id="dfee7-117">Si no se especifica el tipo de datos, una secuencia tiene como valor predeterminado `bigint`.</span><span class="sxs-lookup"><span data-stu-id="dfee7-117">If the data type is not specified, a sequence defaults to `bigint`.</span></span>  
  
## <a name="using-sequences"></a><span data-ttu-id="dfee7-118">Utilizar secuencias</span><span class="sxs-lookup"><span data-stu-id="dfee7-118">Using Sequences</span></span>  
 <span data-ttu-id="dfee7-119">Utilice secuencias en lugar de columnas de identidad en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="dfee7-119">Use sequences instead of identity columns in the following scenarios:</span></span>  
  
-   <span data-ttu-id="dfee7-120">La aplicación requiere un número antes de realizar la inserción en la tabla.</span><span class="sxs-lookup"><span data-stu-id="dfee7-120">The application requires a number before the insert into the table is made.</span></span>  
  
-   <span data-ttu-id="dfee7-121">La aplicación requiere compartir una serie única de números entre varias tablas o varias columnas de una tabla.</span><span class="sxs-lookup"><span data-stu-id="dfee7-121">The application requires sharing a single series of numbers between multiple tables or multiple columns within a table.</span></span>  
  
-   <span data-ttu-id="dfee7-122">La aplicación debe reiniciar la serie de números cuando se alcanza un número especificado.</span><span class="sxs-lookup"><span data-stu-id="dfee7-122">The application must restart the number series when a specified number is reached.</span></span> <span data-ttu-id="dfee7-123">Por ejemplo, después de asignar valores entre 1 y 10, la aplicación comienza de nuevo a asignar valores entre 1 y 10.</span><span class="sxs-lookup"><span data-stu-id="dfee7-123">For example, after assigning values 1 through 10, the application starts assigning values 1 through 10 again.</span></span>  
  
-   <span data-ttu-id="dfee7-124">La aplicación requiere que los valores de secuencia se ordenen por otro campo.</span><span class="sxs-lookup"><span data-stu-id="dfee7-124">The application requires sequence values to be sorted by another field.</span></span> <span data-ttu-id="dfee7-125">La función NEXT VALUE FOR puede aplicar la cláusula OVER a la llamada a la función.</span><span class="sxs-lookup"><span data-stu-id="dfee7-125">The NEXT VALUE FOR function can apply the OVER clause to the function call.</span></span> <span data-ttu-id="dfee7-126">La cláusula OVER garantiza que los valores devueltos se generen en el orden de la cláusula OVER BY de la cláusula ORDER.</span><span class="sxs-lookup"><span data-stu-id="dfee7-126">The OVER clause guarantees that the values returned are generated in the order of the OVER clause's ORDER BY clause.</span></span>  
  
-   <span data-ttu-id="dfee7-127">Una aplicación requiere que se asignen varios números al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="dfee7-127">An application requires multiple numbers to be assigned at the same time.</span></span> <span data-ttu-id="dfee7-128">Por ejemplo, una aplicación necesita reservar cinco números secuenciales.</span><span class="sxs-lookup"><span data-stu-id="dfee7-128">For example, an application needs to reserve five sequential numbers.</span></span> <span data-ttu-id="dfee7-129">Al solicitar los valores de identidad, podrían producirse lagunas en la serie si se emitieron números simultáneamente para otros procesos.</span><span class="sxs-lookup"><span data-stu-id="dfee7-129">Requesting identity values could result in gaps in the series if other processes were simultaneously issued numbers.</span></span> <span data-ttu-id="dfee7-130">Al llamar a sp_sequence_get_range se pueden recuperar de una sola vez varios números de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="dfee7-130">Calling sp_sequence_get_range can retrieve several numbers in the sequence at once.</span></span>  
  
-   <span data-ttu-id="dfee7-131">Necesita cambiar la especificación de la secuencia, como, por ejemplo, el valor de incremento.</span><span class="sxs-lookup"><span data-stu-id="dfee7-131">You need to change the specification of the sequence, such as the increment value.</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="dfee7-132">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="dfee7-132">Limitations</span></span>  
 <span data-ttu-id="dfee7-133">A diferencia de las columnas de identidad, cuyos valores no se pueden cambiar, los valores de secuencia no se protegen automáticamente después de la inserción en la tabla.</span><span class="sxs-lookup"><span data-stu-id="dfee7-133">Unlike identity columns, whose values cannot be changed, sequence values are not automatically protected after insertion into the table.</span></span> <span data-ttu-id="dfee7-134">Para evitar que se cambien los valores de secuencia, utilice un desencadenador de actualización en la tabla para revertir los cambios.</span><span class="sxs-lookup"><span data-stu-id="dfee7-134">To prevent sequence values from being changed, use an update trigger on the table to roll back changes.</span></span>  
  
 <span data-ttu-id="dfee7-135">La singularidad no se aplica automáticamente para los valores de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="dfee7-135">Uniqueness is not automatically enforced for sequence values.</span></span> <span data-ttu-id="dfee7-136">La capacidad de reutilizar los valores de secuencia es por diseño.</span><span class="sxs-lookup"><span data-stu-id="dfee7-136">The ability to reuse sequence values is by design.</span></span> <span data-ttu-id="dfee7-137">Si es necesario que los valores de secuencia de una tabla sean únicos, cree un índice único en la columna.</span><span class="sxs-lookup"><span data-stu-id="dfee7-137">If sequence values in a table are required to be unique, create a unique index on the column.</span></span> <span data-ttu-id="dfee7-138">Si se requiere que los valores de secuencia de una tabla sean únicos en todo un grupo de tablas, cree desencadenadores para evitar los duplicados debidos a las instrucciones de actualización o al ciclo del número de secuencia</span><span class="sxs-lookup"><span data-stu-id="dfee7-138">If sequence values in a table are required to be unique throughout a group of tables, create triggers to prevent duplicates caused by update statements or sequence number cycling.</span></span>  
  
 <span data-ttu-id="dfee7-139">El objeto de secuencia genera los números según su definición, pero el objeto de secuencia no controla cómo se utilizan los números.</span><span class="sxs-lookup"><span data-stu-id="dfee7-139">The sequence object generates numbers according to its definition, but the sequence object does not control how the numbers are used.</span></span> <span data-ttu-id="dfee7-140">Los números de secuencia insertados en una tabla pueden tener lagunas cuando se revierte una transacción, cuando varias tablas comparten un objeto de secuencia o cuando los números de secuencia se asignan sin utilizarlos en tablas.</span><span class="sxs-lookup"><span data-stu-id="dfee7-140">Sequence numbers inserted into a table can have gaps when a transaction is rolled back, when a sequence object is shared by multiple tables, or when sequence numbers are allocated without using them in tables.</span></span> <span data-ttu-id="dfee7-141">Cuando se crea con la opción CACHE, un cierre inesperado, como un error de alimentación, puede perder los números de secuencia de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="dfee7-141">When created with the CACHE option, an unexpected shutdown, such as a power failure, can lose the sequence numbers in the cache.</span></span>  
  
 <span data-ttu-id="dfee7-142">Si hay varias instancias de la función `NEXT VALUE FOR` que especifica el mismo generador de secuencias dentro de una única instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)], todas esas instancias devuelven el mismo valor para una fila determinada procesada por esa instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfee7-142">If there are multiple instances of the `NEXT VALUE FOR` function specifying the same sequence generator within a single [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, all those instances return the same value for a given row processed by that [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="dfee7-143">Este comportamiento es coherente con el estándar ANSI.</span><span class="sxs-lookup"><span data-stu-id="dfee7-143">This behavior is consistent with the ANSI standard.</span></span>  
  
## <a name="typical-use"></a><span data-ttu-id="dfee7-144">Uso típico</span><span class="sxs-lookup"><span data-stu-id="dfee7-144">Typical Use</span></span>  
 <span data-ttu-id="dfee7-145">Para crear un número de secuencia entero que se incremente en 1 de -2.147.483.648 a 2.147.483.647, utilice la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="dfee7-145">To create an integer sequence number that increments by 1 from -2,147,483,648 to 2,147,483,647, use the following statement.</span></span>  
  
```  
CREATE SEQUENCE Schema.SequenceName  
    AS int  
    INCREMENT BY 1 ;  
```  
  
 <span data-ttu-id="dfee7-146">Para crear un número de secuencia entero similar a una columna de identidad que se incrementa en 1 de 1 a 2.147.483.647, utilice la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="dfee7-146">To create an integer sequence number similar to an identity column that increments by 1 from 1 to 2,147,483,647, use the following statement.</span></span>  
  
```  
CREATE SEQUENCE Schema.SequenceName  
    AS int  
    START WITH 1  
    INCREMENT BY 1 ;  
  
```  
  
## <a name="managing-sequences"></a><span data-ttu-id="dfee7-147">Administrar secuencias</span><span class="sxs-lookup"><span data-stu-id="dfee7-147">Managing Sequences</span></span>  
 <span data-ttu-id="dfee7-148">Para obtener información sobre las secuencias, consulte [sys.sequences](/sql/relational-databases/system-catalog-views/sys-sequences-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfee7-148">For information about sequences, query [sys.sequences](/sql/relational-databases/system-catalog-views/sys-sequences-transact-sql).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="dfee7-149">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="dfee7-149">Examples</span></span>  
 <span data-ttu-id="dfee7-150">Encontrará más ejemplos en los temas [CREATE SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-sequence-transact-sql), [NEXT VALUE FOR &#40;Transact-SQL&#41;](/sql/t-sql/functions/next-value-for-transact-sql) y [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfee7-150">There are additional examples in the topics [CREATE SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-sequence-transact-sql), [NEXT VALUE FOR &#40;Transact-SQL&#41;](/sql/t-sql/functions/next-value-for-transact-sql), and [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql).</span></span>  
  
### <a name="a-using-a-sequence-number-in-a-single-table"></a><span data-ttu-id="dfee7-151">A.</span><span class="sxs-lookup"><span data-stu-id="dfee7-151">A.</span></span> <span data-ttu-id="dfee7-152">Usar un número de secuencia en una sola tabla</span><span class="sxs-lookup"><span data-stu-id="dfee7-152">Using a sequence number in a single table</span></span>  
 <span data-ttu-id="dfee7-153">En el siguiente ejemplo se crea un esquema denominado Test, una tabla denominada Orders y una secuencia denominada CountBy1 y, después, se insertan filas en la tabla mediante la función NEXT VALUE FOR.</span><span class="sxs-lookup"><span data-stu-id="dfee7-153">The following example creates a schema named Test, a table named Orders, and a sequence named CountBy1, and then inserts rows into the table using the NEXT VALUE FOR function.</span></span>  
  
```  
--Create the Test schema  
CREATE SCHEMA Test ;  
GO  
  
-- Create a table  
CREATE TABLE Test.Orders  
    (OrderID int PRIMARY KEY,  
    Name varchar(20) NOT NULL,  
    Qty int NOT NULL);  
GO  
  
-- Create a sequence  
CREATE SEQUENCE Test.CountBy1  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
-- Insert three records  
INSERT Test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Tire', 2) ;  
INSERT test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Seat', 1) ;  
INSERT test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Brake', 1) ;  
GO  
  
-- View the table  
SELECT * FROM Test.Orders ;  
GO  
```  
  
 [!INCLUDE[ssResult](../../../includes/ssresult-md.md)]  
  
 `OrderID  Name    Qty`  
  
 `1        Tire    2`  
  
 `2        Seat    1`  
  
 `3        Brake   1`  
  
### <a name="b-calling-next-value-for-before-inserting-a-row"></a><span data-ttu-id="dfee7-154">B.</span><span class="sxs-lookup"><span data-stu-id="dfee7-154">B.</span></span> <span data-ttu-id="dfee7-155">Llamar a NEXT VALUE FOR antes de insertar una fila</span><span class="sxs-lookup"><span data-stu-id="dfee7-155">Calling NEXT VALUE FOR before inserting a row</span></span>  
 <span data-ttu-id="dfee7-156">Utilizando la tabla `Orders` creada en el ejemplo A, el siguiente ejemplo declara una variable denominada `@nextID`y, a continuación, utiliza la función NEXT VALUE FOR para establecer la variable como el siguiente número de secuencia disponible.</span><span class="sxs-lookup"><span data-stu-id="dfee7-156">Using the `Orders` table created in example A, the following example declares a variable named `@nextID`, and then uses the NEXT VALUE FOR function to set the variable to the next available sequence number.</span></span> <span data-ttu-id="dfee7-157">Se supone que la aplicación realiza cierto procesamiento del pedido, como, por ejemplo, proporcionar al cliente el número de `OrderID` de su pedido potencial y, a continuación, valida el pedido.</span><span class="sxs-lookup"><span data-stu-id="dfee7-157">The application is presumed to do some processing of the order, such as providing the customer with the `OrderID` number of their potential order, and then validates the order.</span></span> <span data-ttu-id="dfee7-158">Con independencia de cuánto tiempo pueda llevar este procesamiento y de cuántos pedidos se agreguen durante el proceso, el número original se conserva para que lo utilice esta conexión.</span><span class="sxs-lookup"><span data-stu-id="dfee7-158">No matter how long this processing might take, or how many other orders are added during the process, the original number is preserved for use by this connection.</span></span> <span data-ttu-id="dfee7-159">Finalmente, la instrucción `INSERT` agrega el pedido a la tabla `Orders` .</span><span class="sxs-lookup"><span data-stu-id="dfee7-159">Finally, the `INSERT` statement adds the order to the `Orders` table.</span></span>  
  
```  
DECLARE @NextID int ;  
SET @NextID = NEXT VALUE FOR Test.CountBy1;  
-- Some work happens  
INSERT Test.Orders (OrderID, Name, Qty)  
    VALUES (@NextID, 'Rim', 2) ;  
GO  
  
```  
  
### <a name="c-using-a-sequence-number-in-multiple-tables"></a><span data-ttu-id="dfee7-160">C.</span><span class="sxs-lookup"><span data-stu-id="dfee7-160">C.</span></span> <span data-ttu-id="dfee7-161">Usar un número de secuencia en varias tablas</span><span class="sxs-lookup"><span data-stu-id="dfee7-161">Using a sequence number in multiple tables</span></span>  
 <span data-ttu-id="dfee7-162">En este ejemplo se supone que un proceso de supervisión de la línea de producción recibe una notificación de los eventos que se producen en el taller.</span><span class="sxs-lookup"><span data-stu-id="dfee7-162">This example assumes that a production-line monitoring process receives notification of events that occur throughout the workshop.</span></span> <span data-ttu-id="dfee7-163">Cada evento recibe un número `EventID` único que se incrementa de forma continua.</span><span class="sxs-lookup"><span data-stu-id="dfee7-163">Each event receives a unique and monotonically increasing `EventID` number.</span></span> <span data-ttu-id="dfee7-164">Todos los eventos utilizan el mismo número de secuencia `EventID` para que los informes que combinan todos los eventos puedan identificar cada evento de forma única.</span><span class="sxs-lookup"><span data-stu-id="dfee7-164">All events use the same `EventID` sequence number so that reports that combine all events can uniquely identify each event.</span></span> <span data-ttu-id="dfee7-165">Sin embargo, los datos de evento se almacenan en tres tablas diferentes, dependiendo del tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="dfee7-165">However the event data is stored in three different tables, depending on the type of event.</span></span> <span data-ttu-id="dfee7-166">El ejemplo de código crea un esquema denominado `Audit`, una secuencia denominada `EventCounter`y tres tablas, cada una de las cuales utiliza la secuencia `EventCounter` como valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="dfee7-166">The code example creates a schema named `Audit`, a sequence named `EventCounter`, and three tables which each use the `EventCounter` sequence as a default value.</span></span> <span data-ttu-id="dfee7-167">A continuación el ejemplo agrega las filas a las tres tablas y consulta los resultados.</span><span class="sxs-lookup"><span data-stu-id="dfee7-167">Then the example adds rows to the three tables and queries the results.</span></span>  
  
```  
CREATE SCHEMA Audit ;  
GO  
CREATE SEQUENCE Audit.EventCounter  
    AS int  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
CREATE TABLE Audit.ProcessEvents  
(  
    EventID int PRIMARY KEY CLUSTERED   
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EventCode nvarchar(5) NOT NULL,  
    Description nvarchar(300) NULL  
) ;  
GO  
  
CREATE TABLE Audit.ErrorEvents  
(  
    EventID int PRIMARY KEY CLUSTERED  
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EquipmentID int NULL,  
    ErrorNumber int NOT NULL,  
    EventDesc nvarchar(256) NULL  
) ;  
GO  
  
CREATE TABLE Audit.StartStopEvents  
(  
    EventID int PRIMARY KEY CLUSTERED  
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EquipmentID int NOT NULL,  
    StartOrStop bit NOT NULL  
) ;  
GO  
  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (248, 0) ;  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (72, 0) ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (2735,   
    'Clean room temperature 18 degrees C.') ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (18, 'Spin rate threashold exceeded.') ;  
INSERT Audit.ErrorEvents (EquipmentID, ErrorNumber, EventDesc)   
    VALUES (248, 82, 'Feeder jam') ;  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (248, 1) ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (1841, 'Central feed in bypass mode.') ;  
-- The following statement combines all events, though not all fields.  
SELECT EventID, EventTime, Description FROM Audit.ProcessEvents   
UNION SELECT EventID, EventTime, EventDesc FROM Audit.ErrorEvents   
UNION SELECT EventID, EventTime,   
CASE StartOrStop   
    WHEN 0 THEN 'Start'   
    ELSE 'Stop'  
END   
FROM Audit.StartStopEvents  
ORDER BY EventID ;  
GO  
  
```  
  
 [!INCLUDE[ssResult](../../../includes/ssresult-md.md)]  
  
 `EventID  EventTime                Description`  
  
 `1        2009-11-02 15:00:51.157  Start`  
  
 `2        2009-11-02 15:00:51.160  Start`  
  
 `3        2009-11-02 15:00:51.167  Clean room temperature 18 degrees C.`  
  
 `4        2009-11-02 15:00:51.167  Spin rate threshold exceeded.`  
  
 `5        2009-11-02 15:00:51.173  Feeder jam`  
  
 `6        2009-11-02 15:00:51.177  Stop`  
  
 `7        2009-11-02 15:00:51.180  Central feed in bypass mode.`  
  
### <a name="d-generating-repeating-sequence-numbers-in-a-result-set"></a><span data-ttu-id="dfee7-168">D.</span><span class="sxs-lookup"><span data-stu-id="dfee7-168">D.</span></span> <span data-ttu-id="dfee7-169">Generar números de secuencia repetidos en un conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="dfee7-169">Generating repeating sequence numbers in a result set</span></span>  
 <span data-ttu-id="dfee7-170">En el siguiente ejemplo se muestran dos características de los números de secuencia: recorrer y utilizar `NEXT VALUE FOR` en una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="dfee7-170">The following example demonstrates two features of sequence numbers: cycling, and using `NEXT VALUE FOR` in a select statement.</span></span>  
  
```  
CREATE SEQUENCE CountBy5  
   AS tinyint  
    START WITH 1  
    INCREMENT BY 1  
    MINVALUE 1  
    MAXVALUE 5  
    CYCLE ;  
GO  
  
SELECT NEXT VALUE FOR CountBy5 AS SurveyGroup, Name FROM sys.objects ;  
GO  
```  
  
### <a name="e-generating-sequence-numbers-for-a-result-set-by-using-the-over-clause"></a><span data-ttu-id="dfee7-171">E.</span><span class="sxs-lookup"><span data-stu-id="dfee7-171">E.</span></span> <span data-ttu-id="dfee7-172">Generar números de secuencia para un conjunto de resultados mediante la cláusula OVER</span><span class="sxs-lookup"><span data-stu-id="dfee7-172">Generating sequence numbers for a result set by using the OVER clause</span></span>  
 <span data-ttu-id="dfee7-173">En el ejemplo siguiente se utiliza la cláusula `OVER` para ordenar el conjunto de resultados por `Name` antes de agregar la columna de número de secuencia.</span><span class="sxs-lookup"><span data-stu-id="dfee7-173">The following example uses the `OVER` clause to sort the result set by `Name` before it adds the sequence number column.</span></span>  
  
```  
USE AdventureWorks2012 ;  
GO  
  
CREATE SCHEMA Samples ;  
GO  
  
CREATE SEQUENCE Samples.IDLabel  
    AS tinyint  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
### <a name="f-resetting-the-sequence-number"></a><span data-ttu-id="dfee7-174">F.</span><span class="sxs-lookup"><span data-stu-id="dfee7-174">F.</span></span> <span data-ttu-id="dfee7-175">Restablecer el número de secuencia</span><span class="sxs-lookup"><span data-stu-id="dfee7-175">Resetting the sequence number</span></span>  
 <span data-ttu-id="dfee7-176">El ejemplo E consumió los primeros 79 números de secuencia de `Samples.IDLabel`.</span><span class="sxs-lookup"><span data-stu-id="dfee7-176">Example E consumed the first 79 of the `Samples.IDLabel` sequence numbers.</span></span> <span data-ttu-id="dfee7-177">(Su versión de `AdventureWorks2012` puede devolver un número de resultados diferente). Ejecute lo siguiente para consumir los 79 números de secuencia siguientes (del 80 al 158).</span><span class="sxs-lookup"><span data-stu-id="dfee7-177">(Your version of `AdventureWorks2012` may return a different number of results.) Execute the following to consume the next 79 sequence numbers (80 though 158).</span></span>  
  
```  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
 <span data-ttu-id="dfee7-178">Ejecute la instrucción siguiente para reiniciar la secuencia `Samples.IDLabel` .</span><span class="sxs-lookup"><span data-stu-id="dfee7-178">Execute the following statement to restart the `Samples.IDLabel` sequence.</span></span>  
  
```  
ALTER SEQUENCE Samples.IDLabel  
RESTART WITH 1 ;  
```  
  
 <span data-ttu-id="dfee7-179">Ejecute la instrucción SELECT de nuevo para comprobar que la secuencia `Samples.IDLabel` se ha reiniciado con el número 1.</span><span class="sxs-lookup"><span data-stu-id="dfee7-179">Execute the select statement again to verify that the `Samples.IDLabel` sequence restarted with number 1.</span></span>  
  
```  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
### <a name="g-changing-a-table-from-identity-to-sequence"></a><span data-ttu-id="dfee7-180">G.</span><span class="sxs-lookup"><span data-stu-id="dfee7-180">G.</span></span> <span data-ttu-id="dfee7-181">Cambiar una tabla de identidad a secuencia</span><span class="sxs-lookup"><span data-stu-id="dfee7-181">Changing a table from identity to sequence</span></span>  
 <span data-ttu-id="dfee7-182">En el siguiente ejemplo se crean un esquema y una tabla que contiene tres filas para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="dfee7-182">The following example creates a schema and table containing three rows for the example.</span></span> <span data-ttu-id="dfee7-183">A continuación el ejemplo agrega una nueva columna y quita la columna anterior.</span><span class="sxs-lookup"><span data-stu-id="dfee7-183">Then the example adds a new column and drops the old column.</span></span>  
  
```  
-- Create a schema  
CREATE SCHEMA Test ;  
GO  
  
-- Create a table  
CREATE TABLE Test.Department  
    (  
        DepartmentID smallint IDENTITY(1,1) NOT NULL,  
        Name nvarchar(100) NOT NULL,  
        GroupName nvarchar(100) NOT NULL  
    CONSTRAINT PK_Department_DepartmentID PRIMARY KEY CLUSTERED   
         (DepartmentID ASC)   
    ) ;  
GO  
  
-- Insert three rows into the table  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Engineering', 'Research and Development');  
GO  
  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Tool Design', 'Research and Development');  
GO  
  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Sales', 'Sales and Marketing');  
GO  
  
-- View the table that will be changed  
SELECT * FROM Test.Department ;  
GO  
  
-- End of portion creating a sample table  
--------------------------------------------------------  
-- Add the new column that does not have the IDENTITY property  
ALTER TABLE Test.Department   
    ADD DepartmentIDNew smallint NULL  
GO  
  
-- Copy values from the old column to the new column  
UPDATE Test.Department  
    SET DepartmentIDNew = DepartmentID ;  
GO  
  
-- Drop the primary key constraint on the old column  
ALTER TABLE Test.Department  
    DROP CONSTRAINT [PK_Department_DepartmentID];  
-- Drop the old column  
ALTER TABLE Test.Department  
    DROP COLUMN DepartmentID ;  
GO  
  
-- Rename the new column to the old columns name  
EXEC sp_rename 'Test.Department.DepartmentIDNew',   
    'DepartmentID', 'COLUMN';  
GO  
  
-- Change the new column to NOT NULL  
ALTER TABLE Test.Department  
    ALTER COLUMN DepartmentID smallint NOT NULL ;  
-- Add the unique primary key constraint  
ALTER TABLE Test.Department  
    ADD CONSTRAINT PK_Department_DepartmentID PRIMARY KEY CLUSTERED   
         (DepartmentID ASC) ;  
-- Get the highest current value from the DepartmentID column   
-- and create a sequence to use with the column. (Returns 3.)  
SELECT MAX(DepartmentID) FROM Test.Department ;  
-- Use the next desired value (4) as the START WITH VALUE;  
CREATE SEQUENCE Test.DeptSeq  
    AS smallint  
    START WITH 4  
    INCREMENT BY 1 ;  
GO  
  
-- Add a default value for the DepartmentID column  
ALTER TABLE Test.Department  
    ADD CONSTRAINT DefSequence DEFAULT (NEXT VALUE FOR Test.DeptSeq)   
        FOR DepartmentID;  
GO  
  
-- View the result  
SELECT DepartmentID, Name, GroupName  
FROM Test.Department ;   
-- Test insert  
INSERT Test.Department (Name, GroupName)  
    VALUES ('Audit', 'Quality Assurance') ;  
GO  
  
-- View the result  
SELECT DepartmentID, Name, GroupName  
FROM Test.Department ;  
GO  
  
```  
  
 <span data-ttu-id="dfee7-184">Las instrucciones [!INCLUDE[tsql](../../../includes/tsql-md.md)] que utilizan `SELECT *` recibirán la nueva columna como última columna, no como primera.</span><span class="sxs-lookup"><span data-stu-id="dfee7-184">[!INCLUDE[tsql](../../../includes/tsql-md.md)] statements that use `SELECT *` will receive the new column as the last column instead of the first column.</span></span> <span data-ttu-id="dfee7-185">Si esto no es aceptable, debe crear una tabla completamente nueva, mover los datos a ella y, a continuación, volver a crear los permisos en la nueva tabla.</span><span class="sxs-lookup"><span data-stu-id="dfee7-185">If this is not acceptable, then you must create an entirely new table, move the data to it, and then recreate the permissions on the new table.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="dfee7-186">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="dfee7-186">Related Content</span></span>  
 [<span data-ttu-id="dfee7-187">CREATE SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dfee7-187">CREATE SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-sequence-transact-sql)  
  
 [<span data-ttu-id="dfee7-188">ALTER SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dfee7-188">ALTER SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-sequence-transact-sql)  
  
 [<span data-ttu-id="dfee7-189">DROP SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dfee7-189">DROP SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-sequence-transact-sql)  
  
 [<span data-ttu-id="dfee7-190">IDENTITY &#40;propiedad de Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dfee7-190">IDENTITY &#40;Property&#41; &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql-identity-property)  
  
  
