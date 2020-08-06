---
title: Enumerar los paquetes disponibles mediante programación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- programmatically enumerate packages [SSIS]
- existence testing [Integration Services]
- enumerating packages [Integration Services]
ms.assetid: 254ec7ee-d3ff-4361-8995-46e9b9c4dc95
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 053f2e598b1cc18e68ee2182092188367ee7f10c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744736"
---
# <a name="enumerating-available-packages-programmatically"></a><span data-ttu-id="1bee1-102">Enumerar los paquetes disponibles mediante programación</span><span class="sxs-lookup"><span data-stu-id="1bee1-102">Enumerating Available Packages Programmatically</span></span>
  <span data-ttu-id="1bee1-103">Cuando trabaja mediante programación con paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , puede determinar si existe un paquete o una carpeta individual o enumerar los paquetes guardados que están disponible para cargarse y ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="1bee1-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine whether an individual package or folder exists, or to enumerate the saved packages that are available to load and execute.</span></span> <span data-ttu-id="1bee1-104">La clase <xref:Microsoft.SqlServer.Dts.Runtime.Application> del espacio de nombres <xref:Microsoft.SqlServer.Dts.Runtime> proporciona diferentes métodos para satisfacer estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="1bee1-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>  
  
##  <a name="determining-whether-a-package-or-folder-exists"></a><a name="exists"></a> <span data-ttu-id="1bee1-105">Determinar si existe un paquete o una carpeta</span><span class="sxs-lookup"><span data-stu-id="1bee1-105">Determining Whether a Package or Folder Exists</span></span>  
 <span data-ttu-id="1bee1-106">Para determinar mediante programación si existe un paquete guardado, llame a uno de los métodos siguientes antes de intentar cargarlo y ejecutarlo:</span><span class="sxs-lookup"><span data-stu-id="1bee1-106">To determine programmatically whether a saved package exists, call one of the following methods before attempting to load and run it:</span></span>  
  
|<span data-ttu-id="1bee1-107">Ubicación de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="1bee1-107">Storage Location</span></span>|<span data-ttu-id="1bee1-108">Método que se llama</span><span class="sxs-lookup"><span data-stu-id="1bee1-108">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="1bee1-109">Almacén de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="1bee1-109">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnSqlServer%2A>|  
  
 <span data-ttu-id="1bee1-110">Para determinar mediante programación si existe una carpeta antes de intentar enumerar los paquetes almacenados en ella, llame a uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1bee1-110">To determine programmatically whether a folder exists before attempting to list the packages stored in it, call one of the following methods:</span></span>  
  
|<span data-ttu-id="1bee1-111">Ubicación de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="1bee1-111">Storage Location</span></span>|<span data-ttu-id="1bee1-112">Método que se llama</span><span class="sxs-lookup"><span data-stu-id="1bee1-112">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="1bee1-113">Almacén de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="1bee1-113">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnSqlServer%2A>|  
  
 [<span data-ttu-id="1bee1-114">Volver arriba</span><span class="sxs-lookup"><span data-stu-id="1bee1-114">Back to top</span></span>](#top)  
  
##  <a name="enumerating-available-packages"></a><a name="listing"></a> <span data-ttu-id="1bee1-115">Enumerar los paquetes disponibles</span><span class="sxs-lookup"><span data-stu-id="1bee1-115">Enumerating Available Packages</span></span>  
 <span data-ttu-id="1bee1-116">Para obtener una lista de los paquetes guardados mediante programación, llame a uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1bee1-116">To obtain a list of saved packages programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="1bee1-117">Ubicación de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="1bee1-117">Storage Location</span></span>|<span data-ttu-id="1bee1-118">Método que se llama</span><span class="sxs-lookup"><span data-stu-id="1bee1-118">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="1bee1-119">Almacén de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="1bee1-119">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A>|  
  
 <span data-ttu-id="1bee1-120">Los ejemplos siguientes son aplicaciones de consola que muestran el uso de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="1bee1-120">The following samples are console applications that demonstrate the use of these methods.</span></span>  
  
###  <a name="example-ssis-package-store"></a><a name="listing_store"></a> <span data-ttu-id="1bee1-121">Ejemplo (almacén de paquetes SSIS)</span><span class="sxs-lookup"><span data-stu-id="1bee1-121">Example (SSIS Package Store)</span></span>  
 <span data-ttu-id="1bee1-122">Utilice el método <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A> para enumerar los paquetes almacenados en el almacén de paquetes SSIS.</span><span class="sxs-lookup"><span data-stu-id="1bee1-122">Use the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A> method to list packages stored in the SSIS Package Store.</span></span> <span data-ttu-id="1bee1-123">Las ubicaciones de almacenamiento predeterminadas que administra el almacén de paquetes SSIS son Sistema de archivos y MSDB.</span><span class="sxs-lookup"><span data-stu-id="1bee1-123">The default storage locations that are managed by the SSIS Package store are File System and MSDB.</span></span> <span data-ttu-id="1bee1-124">Puede crear carpetas lógicas adicionales dentro de estas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="1bee1-124">You can create additional logical folders within these locations.</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim sqlFolder As String  
    Dim sqlServer As String  
  
    Dim ssisApplication As Application  
    Dim sqlPackages As PackageInfos  
    Dim sqlPackage As PackageInfo  
  
    sqlServer = "."  
  
    ssisApplication = New Application()  
  
    ' Get packages stored in MSDB.  
    sqlFolder = "MSDB"  
    sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer)  
    If sqlPackages.Count > 0 Then  
      Console.WriteLine("Packages stored in MSDB:")  
      For Each sqlPackage In sqlPackages  
        Console.WriteLine(sqlPackage.Name)  
      Next  
      Console.WriteLine()  
    End If  
  
    ' Get packages stored in the File System.  
    sqlFolder = "File System"  
    sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer)  
    If sqlPackages.Count > 0 Then  
      Console.WriteLine("Packages stored in the File System:")  
      For Each sqlPackage In sqlPackages  
        Console.WriteLine(sqlPackage.Name)  
      Next  
    End If  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace EnumeratePackagesSSIS_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
  
      string sqlFolder;  
      string sqlServer;  
  
      Application ssisApplication;  
      PackageInfos sqlPackages;  
  
      sqlServer = ".";  
  
      ssisApplication = new Application();  
  
      // Get packages stored in MSDB.  
      sqlFolder = "MSDB";  
      sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer);  
      if (sqlPackages.Count > 0)  
      {  
        Console.WriteLine("Packages stored in MSDB:");  
        foreach (PackageInfo sqlPackage in sqlPackages)  
        {  
          Console.WriteLine(sqlPackage.Name);  
        }  
        Console.WriteLine();  
      }  
  
      // Get packages stored in the File System.  
      sqlFolder = "File System";  
      sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer);  
      if (sqlPackages.Count > 0)  
      {  
        Console.WriteLine("Packages stored in the File System:");  
        foreach (PackageInfo sqlPackage in sqlPackages)  
        {  
          Console.WriteLine(sqlPackage.Name);  
        }  
      }  
  
      Console.Read();  
  
    }  
  
  }  
  
}  
```  
  
 [<span data-ttu-id="1bee1-125">Volver arriba</span><span class="sxs-lookup"><span data-stu-id="1bee1-125">Back to top</span></span>](#top)  
  
###  <a name="example-sql-server"></a><a name="listing_sql"></a> <span data-ttu-id="1bee1-126">Ejemplo (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1bee1-126">Example (SQL Server)</span></span>  
 <span data-ttu-id="1bee1-127">Utilice el método <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A> para enumerar los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] almacenados en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bee1-127">Use the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A> method to list [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that are stored in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim sqlFolder As String  
    Dim sqlServer As String  
    Dim sqlUser As String  
    Dim sqlPassword As String  
  
    Dim ssisApplication As Application  
    Dim sqlPackages As PackageInfos  
    Dim sqlPackage As PackageInfo  
  
    sqlFolder = String.Empty  
    sqlServer = "(local)"  
    sqlUser = String.Empty  
    sqlPassword = String.Empty  
  
    ssisApplication = New Application()  
  
    sqlPackages = ssisApplication.GetPackageInfos(sqlFolder, sqlServer, sqlUser, sqlPassword)  
  
    For Each sqlPackage In sqlPackages  
      Console.WriteLine(sqlPackage.Name)  
    Next  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace EnumeratePackagesSql_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
  
      string sqlFolder;  
      string sqlServer;  
      string sqlUser;  
      string sqlPassword;  
  
      Application ssisApplication;  
      PackageInfos sqlPackages;  
  
      sqlFolder = String.Empty;  
      sqlServer = "(local)";  
      sqlUser = String.Empty;  
      sqlPassword = String.Empty;  
  
      ssisApplication = new Application();  
  
      sqlPackages = ssisApplication.GetPackageInfos(sqlFolder, sqlServer, sqlUser, sqlPassword);  
  
      foreach (PackageInfo sqlPackage in sqlPackages)  
      {  
        Console.WriteLine(sqlPackage.Name);  
      }  
  
      Console.Read();  
  
    }  
  }  
}  
```  
  
 [<span data-ttu-id="1bee1-128">Volver arriba</span><span class="sxs-lookup"><span data-stu-id="1bee1-128">Back to top</span></span>](#top)  
  
<span data-ttu-id="1bee1-129">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="1bee1-129">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="1bee1-130">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="1bee1-130">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="1bee1-131">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="1bee1-131">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="1bee1-132">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="1bee1-132">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bee1-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1bee1-133">See Also</span></span>  
 [<span data-ttu-id="1bee1-134">Administración de paquetes &#40;servicio SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1bee1-134">Package Management &#40;SSIS Service&#41;</span></span>](../service/package-management-ssis-service.md)  
  
  
