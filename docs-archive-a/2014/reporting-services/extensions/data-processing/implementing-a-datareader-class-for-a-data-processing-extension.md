---
title: Implementar una clase DataReader para una extensión de procesamiento de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], data readers
- data readers [Reporting Services]
- DataReader class
- read-only data
ms.assetid: 23e286e7-6074-4fbe-be29-203420d6c3d0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7c9e55741c72d624b7149435ced90550135d8b4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750490"
---
# <a name="implementing-a-datareader-class-for-a-data-processing-extension"></a><span data-ttu-id="080bb-102">Implementar una clase DataReader para una extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="080bb-102">Implementing a DataReader Class for a Data Processing Extension</span></span>
  <span data-ttu-id="080bb-103">El objeto **DataReader** permite a un cliente recuperar de un origen de datos una secuencia de datos de solo lectura y solo avance.</span><span class="sxs-lookup"><span data-stu-id="080bb-103">The **DataReader** object enables a client to retrieve a read-only, forward-only stream of data from a data source.</span></span> <span data-ttu-id="080bb-104">Los resultados se devuelven a medida que se ejecuta la consulta y se almacenan en el búfer de red en el cliente hasta que se los solicita mediante el método **Read** de la clase **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="080bb-104">Results are returned as the query executes and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader** class.</span></span> <span data-ttu-id="080bb-105">Para crear una clase **DataReader**, implemente <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> y, si quiere, <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension>.</span><span class="sxs-lookup"><span data-stu-id="080bb-105">To create a **DataReader** class, implement <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> and optionally implement <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension>.</span></span> <span data-ttu-id="080bb-106">Al usar un objeto **DataReader**, aumenta el rendimiento de la aplicación tanto al recuperar datos en cuanto están disponibles en lugar de esperar a que se devuelvan los resultados completos de la consulta, como (de forma predeterminada) al almacenar solo una fila a la vez en la memoria, con lo que se reduce la sobrecarga del sistema.</span><span class="sxs-lookup"><span data-stu-id="080bb-106">Using a **DataReader** object increases application performance both by retrieving data as soon as it is available, rather than waiting for the entire results of the query to be returned, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="080bb-107">Después de crear una instancia de la clase **Command**, cree un objeto **DataReader** al llamar a **Command.ExecuteReader** para recuperar filas del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="080bb-107">After creating an instance of your **Command** class, you create a **DataReader** object by calling **Command.ExecuteReader** to retrieve rows from the data source.</span></span> <span data-ttu-id="080bb-108">La implementación de **DataReader** debe proporcionar dos capacidades básicas: el acceso de solo avance a los conjuntos de resultados obtenidos al ejecutar un comando y el acceso a los tipos de columna, los nombres y los valores dentro de cada fila.</span><span class="sxs-lookup"><span data-stu-id="080bb-108">The **DataReader** implementation must provide two basic capabilities: forward-only access over the result sets obtained by executing a command and access to the column types, names, and values within each row.</span></span> <span data-ttu-id="080bb-109">Los clientes usan el método **Read** del objeto **DataReader** para obtener una fila de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="080bb-109">Clients use the **Read** method of the **DataReader** object to obtain a row from the results of the query.</span></span>  
  
 <span data-ttu-id="080bb-110">En el Diseñador de informes, el objeto **DataReader** se usa para recuperar una lista de campos, así como información de esquema sobre el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="080bb-110">In Report Designer, your **DataReader** object is used to retrieve a list of fields as well as schema information about the result set.</span></span> <span data-ttu-id="080bb-111">Esto se logra al implementar los métodos **GetName**, **GetValue**, **GetFieldType** y **GetOrdinal** de la interfaz <xref:Microsoft.ReportingServices.DataProcessing.IDataReader>.</span><span class="sxs-lookup"><span data-stu-id="080bb-111">This is accomplished by implementing the **GetName**, **GetValue**, **GetFieldType,** and **GetOrdinal** methods of the <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> interface.</span></span>  
  
 <span data-ttu-id="080bb-112">La interfaz <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension> le permite proporcionar información de agregaciones concretas acerca del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="080bb-112">The <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension> interface allows you to supply specific aggregation information about your result set.</span></span> <span data-ttu-id="080bb-113">Para obtener un ejemplo de implementación de la clase **DataReader**, vea [Ejemplos del producto SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="080bb-113">For a sample **DataReader** class implementation, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="080bb-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="080bb-114">See Also</span></span>  
 <span data-ttu-id="080bb-115">[Extensiones de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="080bb-115">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="080bb-116">[Implementar una extensión de procesamiento de datos](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="080bb-116">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="080bb-117">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="080bb-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
