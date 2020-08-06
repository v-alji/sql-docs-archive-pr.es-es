---
title: Asistente de compilación nativa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
f1_keywords:
- sql12.swb.nativecompilationwizard.f1
- swb.nativecompilationwizard.f1
ms.assetid: d3898a47-2985-4a08-bc70-fd8331a01b7b
author: rothja
ms.author: jroth
ms.openlocfilehash: b2182d89489af5da8bc3b85b89484fbbf72e4dfa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750962"
---
# <a name="native-compilation-advisor"></a><span data-ttu-id="67f72-102">Asistente de compilación nativa</span><span class="sxs-lookup"><span data-stu-id="67f72-102">Native Compilation Advisor</span></span>
  <span data-ttu-id="67f72-103">La herramienta de informes de rendimiento de transacciones (vea [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)) le informa sobre los procedimientos almacenados interpretados de la base de datos que se beneficiarían si se convierten para utilizar la compilación nativa.</span><span class="sxs-lookup"><span data-stu-id="67f72-103">Transaction performance reports tool (see [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)) informs you about which interpreted stored procedures in your database will benefit if ported to use native compilation.</span></span> <span data-ttu-id="67f72-104">Después de identificar el procedimiento almacenado que desea convertir para que utilice la compilación nativa, puede utilizar el Asistente de compilación nativa para que le ayude a migrar el procedimiento almacenado interpretado a la compilación nativa.</span><span class="sxs-lookup"><span data-stu-id="67f72-104">After you identify a stored procedure that you would like to port to use native compilation, you can use the native compilation advisor to help you migrate the interpreted stored procedure to native compilation.</span></span> <span data-ttu-id="67f72-105">Para obtener más información acerca de los procedimientos almacenados compilados de forma nativa, vea [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="67f72-105">For more information about natively compiled stored procedures, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="67f72-106">Para empezar, conéctese a la instancia que contiene el procedimiento almacenado interpretado.</span><span class="sxs-lookup"><span data-stu-id="67f72-106">To begin, connect to the instance that contains the interpreted stored procedure.</span></span> <span data-ttu-id="67f72-107">Puede conectarse a una instancia de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]o [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67f72-107">You can connect to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], or [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] instance.</span></span> <span data-ttu-id="67f72-108">Sin embargo, si desea realizar una operación de migración con el asistente, debe conectarse a una instancia de [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] que tenga habilitada la funcionalidad de OLTP en memoria.</span><span class="sxs-lookup"><span data-stu-id="67f72-108">However, if you wish to perform a migration operation with the advisor, you must connect to a [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] instance on which In-Memory OLTP functionality is enabled.</span></span> <span data-ttu-id="67f72-109">Para obtener más información acerca de los requisitos de OLTP en memoria, vea [Requirements for Using Memory-Optimized Tables](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="67f72-109">For more information about In-Memory OLTP requirements, see [Requirements for Using Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="67f72-110">Para obtener más información sobre las metodologías de migración, vea [OLTP en memoria: patrones de carga de trabajo comunes y consideraciones sobre la migración](https://msdn.microsoft.com/library/dn673538.aspx).</span><span class="sxs-lookup"><span data-stu-id="67f72-110">For information about migration methodologies, see [In-Memory OLTP - Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx).</span></span>  
  
## <a name="walkthrough-using-the-native-compilation-advisor"></a><span data-ttu-id="67f72-111">Tutorial del uso del Asistente de compilación nativa</span><span class="sxs-lookup"><span data-stu-id="67f72-111">Walkthrough Using the Native Compilation Advisor</span></span>  
 <span data-ttu-id="67f72-112">En el **Explorador de objetos**, haga clic con el botón secundario en el procedimiento almacenado que desea convertir, y seleccione **Asistente de compilación nativa**.</span><span class="sxs-lookup"><span data-stu-id="67f72-112">In **Object Explorer**, right click the stored procedure you want to convert, and select **Native Compilation Advisor**.</span></span> <span data-ttu-id="67f72-113">Se mostrará la página de bienvenida del **Asistente de compilación nativa de procedimiento almacenado**.</span><span class="sxs-lookup"><span data-stu-id="67f72-113">This will display the welcome page for the **Stored Procedure Native Compilation Advisor**.</span></span> <span data-ttu-id="67f72-114">Haga clic en **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="67f72-114">Click **Next** to continue.</span></span>  
  
### <a name="stored-procedure-validation"></a><span data-ttu-id="67f72-115">Validación del procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="67f72-115">Stored Procedure Validation</span></span>  
 <span data-ttu-id="67f72-116">Esta página le indicará si el procedimiento almacenado utiliza construcciones que no son compatibles con la compilación nativa.</span><span class="sxs-lookup"><span data-stu-id="67f72-116">This page will report if the stored procedure uses any constructs that are not compatible with native compilation.</span></span> <span data-ttu-id="67f72-117">Puede hacer clic en **Siguiente** para ver los detalles.</span><span class="sxs-lookup"><span data-stu-id="67f72-117">You can click **Next** to see details.</span></span> <span data-ttu-id="67f72-118">Si hay construcciones que no son compatibles con la compilación nativa, puede hacer clic en **Siguiente** para ver los detalles.</span><span class="sxs-lookup"><span data-stu-id="67f72-118">If there are constructs that are not compatible with native compilation, you can click **Next** to see details.</span></span>  
  
### <a name="stored-procedure-validation-result"></a><span data-ttu-id="67f72-119">Resultado de la validación del procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="67f72-119">Stored Procedure Validation Result</span></span>  
 <span data-ttu-id="67f72-120">Si hay construcciones que no son compatibles con la compilación nativa, la página **Resultado de la validación del procedimiento almacenado** mostrará los detalles.</span><span class="sxs-lookup"><span data-stu-id="67f72-120">If there are constructs that are not compatible with native compilation, the **Stored Procedure Validation Result** page will display details.</span></span> <span data-ttu-id="67f72-121">Puede generar un informe (haga clic en **Generar informe**), salir del **Asistente de compilación nativa**y actualizar el código para que sea compatible con la compilación nativa.</span><span class="sxs-lookup"><span data-stu-id="67f72-121">You can generate a report (click **Generate Report**), exit the **Native Compilation Advisor**, and update your code so that it is compatible with native compilation.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="67f72-122">Ejemplo de código</span><span class="sxs-lookup"><span data-stu-id="67f72-122">Code Sample</span></span>  
 <span data-ttu-id="67f72-123">El ejemplo siguiente muestra un procedimiento almacenado interpretado y el procedimiento almacenado equivalente para la compilación nativa.</span><span class="sxs-lookup"><span data-stu-id="67f72-123">The following sample shows an interpreted stored procedure and the equivalent stored procedure for native compilation.</span></span> <span data-ttu-id="67f72-124">El ejemplo supone que existe un directorio denominado c:\data.</span><span class="sxs-lookup"><span data-stu-id="67f72-124">The sample assumes a directory called c:\data.</span></span>  
  
```sql  
CREATE DATABASE Demo  
ON  
PRIMARY(NAME = [Demo_data],  
FILENAME = 'C:\DATA\Demo_data.mdf', size=500MB)  
, FILEGROUP [Demo_fg] CONTAINS MEMORY_OPTIMIZED_DATA(  
NAME = [Demo_dir],  
FILENAME = 'C:\DATA\Demo_dir')  
LOG ON (name = [Demo_log], Filename='C:\DATA\Demo_log.ldf', size=500MB)  
COLLATE Latin1_General_100_BIN2;  
GO  
USE Demo;  
GO  
  
CREATE TABLE [dbo].[SalesOrders]  
(  
     [order_id] [int] NOT NULL,  
     [order_date] [datetime] NOT NULL,  
     [order_status] [tinyint] NOT NULL  
  
CONSTRAINT [PK_SalesOrders] PRIMARY KEY NONCLUSTERED HASH   
(  
     [order_id]  
)WITH ( BUCKET_COUNT = 2097152)  
)WITH ( MEMORY_OPTIMIZED = ON )  
  
go  
  
CREATE PROCEDURE [dbo].[InsertOrder] @id INT, @date DATETIME2, @status TINYINT  
AS   
BEGIN   
  
  INSERT dbo.SalesOrders VALUES (@id, @date, @status)  
  
END  
  
go  
  
CREATE PROCEDURE [dbo].[InsertOrderXTP] @id INT, @date DATETIME2, @status TINYINT  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS   
BEGIN ATOMIC WITH   
(    TRANSACTION ISOLATION LEVEL = SNAPSHOT,  
     LANGUAGE = N'us_english')  
  
  INSERT dbo.SalesOrders VALUES (@id, @date, @status)  
  
END  
go  
  
select * from SalesOrders  
go  
exec dbo.InsertOrder @id= 10, @date = '1956-01-01 12:00:00', @status = 1 ;  
exec dbo.InsertOrderXTP @id= 11, @date = '1956-01-01 12:01:00', @status = 2 ;  
select * from SalesOrders  
```  
  
## <a name="see-also"></a><span data-ttu-id="67f72-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67f72-125">See Also</span></span>  
 [<span data-ttu-id="67f72-126">Migrar a OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="67f72-126">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
