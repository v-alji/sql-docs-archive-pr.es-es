---
title: Guardar un paquete mediante programación | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- programmatically saving a package
- saving a package programmatically
ms.assetid: 4204f817-d5df-475a-9338-d7f01305d566
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2879c4213b2c9c0bf395c103de0d1bc37e4daab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671136"
---
# <a name="saving-a-package-programmatically"></a><span data-ttu-id="f53aa-102">Guardar un paquete mediante programación</span><span class="sxs-lookup"><span data-stu-id="f53aa-102">Saving a Package Programmatically</span></span>
  <span data-ttu-id="f53aa-103">Después de generar un nuevo paquete o modificar uno existente mediante programación, por lo general desea guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="f53aa-103">After building a new package programmatically, or modifying an existing one, you usually want to save your changes.</span></span>  
  
 <span data-ttu-id="f53aa-104">Todos los métodos utilizados en este tema para guardar paquetes requieren una referencia al ensamblado `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="f53aa-104">All of the methods used in this topic to save packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="f53aa-105">Después de agregar la referencia en un proyecto nuevo, importe el <xref:Microsoft.SqlServer.Dts.Runtime> espacio de nombres con una `using` `Imports` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="f53aa-105">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
## <a name="saving-a-package-programmatically"></a><span data-ttu-id="f53aa-106">Guardar un paquete mediante programación</span><span class="sxs-lookup"><span data-stu-id="f53aa-106">Saving a Package Programmatically</span></span>  
 <span data-ttu-id="f53aa-107">Para guardar un paquete mediante programación, llame a uno de los métodos siguientes de la clase de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <xref:Microsoft.SqlServer.Dts.Runtime.Application>:</span><span class="sxs-lookup"><span data-stu-id="f53aa-107">To save a package programmatically, call one of the following methods of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <xref:Microsoft.SqlServer.Dts.Runtime.Application> class:</span></span>  
  
|<span data-ttu-id="f53aa-108">Ubicación de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="f53aa-108">Storage Location</span></span>|<span data-ttu-id="f53aa-109">Método que se llama</span><span class="sxs-lookup"><span data-stu-id="f53aa-109">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="f53aa-110">Archivo</span><span class="sxs-lookup"><span data-stu-id="f53aa-110">File</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToXml%2A>|  
|<span data-ttu-id="f53aa-111">Almacén de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="f53aa-111">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToSqlServer%2A><br /><br /> <span data-ttu-id="f53aa-112">or</span><span class="sxs-lookup"><span data-stu-id="f53aa-112">or</span></span><br /><br /> <xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToSqlServerAs%2A>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f53aa-113">Los métodos de la clase <xref:Microsoft.SqlServer.Dts.Runtime.Application> para trabajar con el almacén de paquetes SSIS solo admiten "." o el nombre del servidor local.</span><span class="sxs-lookup"><span data-stu-id="f53aa-113">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store only support "." or the server name for the local server.</span></span> <span data-ttu-id="f53aa-114">No puede utilizar" "(local)" ni "localhost".</span><span class="sxs-lookup"><span data-stu-id="f53aa-114">You cannot use "(local)" or "localhost".</span></span>  
  
<span data-ttu-id="f53aa-115">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f53aa-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f53aa-116">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="f53aa-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f53aa-117">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="f53aa-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f53aa-118">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="f53aa-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f53aa-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f53aa-119">See Also</span></span>  
 [<span data-ttu-id="f53aa-120">Guardar paquetes</span><span class="sxs-lookup"><span data-stu-id="f53aa-120">Save Packages</span></span>](../save-packages.md)  
  
  
