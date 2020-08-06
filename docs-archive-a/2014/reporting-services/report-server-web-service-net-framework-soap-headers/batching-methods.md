---
title: Métodos de procesamiento por lotes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- methods [Reporting Services], batches
- BatchHeader SOAP header
- Web service [Reporting Services], methods
- Report Server Web service, batching
- batches [Reporting Services]
- XML Web service [Reporting Services], methods
- locking [Reporting Services]
- multiple Web service methods
ms.assetid: 86435534-c9fe-4b49-b88c-7fb6d21976b0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c778da186fdbbfaed17b9635d9ca7309a369552b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676332"
---
# <a name="batching-methods"></a><span data-ttu-id="2886b-102">Métodos de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="2886b-102">Batching Methods</span></span>
  <span data-ttu-id="2886b-103">El uso de encabezados SOAP en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] le permite incluir varios métodos de servicio web en una única operación.</span><span class="sxs-lookup"><span data-stu-id="2886b-103">The use of SOAP headers in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] enables you to include multiple Web service methods in a single operation.</span></span> <span data-ttu-id="2886b-104">Los métodos se ejecutan dentro del ámbito de una única transacción de base de datos, en el orden en el que se llaman.</span><span class="sxs-lookup"><span data-stu-id="2886b-104">Methods run within the scope of a single database transaction, in the order in which they are called.</span></span>  
  
 <span data-ttu-id="2886b-105">La reversión es una ventaja de la utilización de operaciones por lotes con varios métodos.</span><span class="sxs-lookup"><span data-stu-id="2886b-105">Rollback is one advantage of using multiple-method batch operations.</span></span> <span data-ttu-id="2886b-106">Si se produce un error en alguna de las llamadas a los métodos mientras se está ejecutando un lote, el servidor de informes deja de ejecutarlo y revierte cualquier operación anterior.</span><span class="sxs-lookup"><span data-stu-id="2886b-106">If an error occurs on any of the method calls while a batch is running, the report server stops running the batch and rolls back any previous operations.</span></span> <span data-ttu-id="2886b-107">Esto es útil cuando una llamada a un método depende de que otras llamadas a métodos de ese lote se completen correctamente.</span><span class="sxs-lookup"><span data-stu-id="2886b-107">This is useful when a method call depends on the successful completion of other method calls in that batch.</span></span>  
  
 <span data-ttu-id="2886b-108">El servicio web no proporciona semántica de bloqueo para las operaciones por lotes con varios métodos.</span><span class="sxs-lookup"><span data-stu-id="2886b-108">The Web service does not provide locking semantics for multiple-method batch operations.</span></span> <span data-ttu-id="2886b-109">Las filas de la base de datos del servidor de informes no se bloquean para actualizar hasta que el mensaje se envía al servidor y se llama al comando Execute.</span><span class="sxs-lookup"><span data-stu-id="2886b-109">Rows in the report server database are not locked for updating until the message is sent to the server and the Execute command is called.</span></span>  
  
 <span data-ttu-id="2886b-110">No hay tampoco ningún control de la simultaneidad para garantizar que la base de datos no ha cambiado desde que se leyeron los últimos datos.</span><span class="sxs-lookup"><span data-stu-id="2886b-110">There are also no concurrency controls to guarantee that the database has not changed since the data was last read.</span></span> <span data-ttu-id="2886b-111">Si dos clientes modifican el mismo elemento, la última actualización tiene éxito si los parámetros todavía son válidos (por ejemplo, el nombre del elemento no se ha cambiado).</span><span class="sxs-lookup"><span data-stu-id="2886b-111">If two clients modify the same item, the last update succeeds if the parameters are still valid (for example, the item has not been renamed).</span></span>  
  
 <span data-ttu-id="2886b-112">El ejemplo siguiente llama al método <xref:ReportService2005.ReportingService2005.CreateFolder%2A> tres veces y ejecuta estas llamadas como un único lote.</span><span class="sxs-lookup"><span data-stu-id="2886b-112">The following example calls the <xref:ReportService2005.ReportingService2005.CreateFolder%2A> method three times and runs these calls as a single batch.</span></span> <span data-ttu-id="2886b-113">Si cualquiera de las llamadas a <xref:ReportService2005.ReportingService2005.CreateFolder%2A> no puede realizarse, se cancela el lote completo.</span><span class="sxs-lookup"><span data-stu-id="2886b-113">If any of the calls to <xref:ReportService2005.ReportingService2005.CreateFolder%2A> fail, the entire batch is canceled.</span></span>  
  
```vb  
Imports System  
Imports System.Web.Services.Protocols  
Imports myNamespace.MyReferenceName  
  
Class Sample  
    Sub Main(args() As String)  
        Dim rs As New ReportingService2005()  
        rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
      ' Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/ReportService2005.asmx"  
  
        Dim bh As New BatchHeader()  
  
        bh.BatchId = service.CreateBatch()  
        rs.BatchHeaderValue = bh  
        rs.CreateFolder("New Folder1", "/", Nothing)  
        rs.CreateFolder("New Folder2", "/", Nothing)  
        rs.CreateFolder("New Folder3", "/", Nothing)  
  
        Console.WriteLine("Creating folders...")  
        rs.BatchHeaderValue = bh  
        rs.ExecuteBatch()  
        Console.WriteLine("Folders created successfully.")  
  
        rs.BatchHeaderValue = Nothing  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Web.Services.Protocols;   
using myNamespace.MyReferenceName;  
  
class Sample  
{  
    static void Main(string[] args)  
    {  
        ReportingService2005 rs = new ReportingService2005();  
        rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
      // Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/ReportService2005.asmx"  
  
        BatchHeader bh = new BatchHeader();  
  
        bh1.BatchID = service.CreateBatch();  
        rs.BatchHeaderValue = bh;  
        rs.CreateFolder("New Folder1", "/", null);  
        rs.CreateFolder("New Folder2", "/", null);  
        rs.CreateFolder("New Folder3", "/", null);  
  
        Console.WriteLine("Creating folders...");  
        rs.BatchHeaderValue = bh1;  
        rs.ExecuteBatch();  
        Console.WriteLine("Folders created successfully.");  
  
        rs.BatchHeaderValue = null;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2886b-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2886b-114">See Also</span></span>  
 <xref:ReportService2005.ReportingService2005.CancelBatch%2A>   
 <xref:ReportService2005.ReportingService2005.CreateBatch%2A>   
 <span data-ttu-id="2886b-115">[Referencia técnica &#40;SSRS&#41;](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2886b-115">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="2886b-116">Utilizar los encabezados SOAP de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2886b-116">Using Reporting Services SOAP Headers</span></span>](using-reporting-services-soap-headers.md)  
  
  
