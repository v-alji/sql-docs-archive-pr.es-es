---
title: Guardar un informe en una biblioteca de SharePoint (Generador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4daa1eee-78b7-43d0-8b22-4a98e8fa66ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 49878a0d7115a11e804382cb5139aa0ec7b3d254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672770"
---
# <a name="save-a-report-to-a-sharepoint-library-report-builder"></a><span data-ttu-id="5c9fa-102">Guardar un informe en una biblioteca de SharePoint (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="5c9fa-102">Save a Report to a SharePoint Library (Report Builder)</span></span>
  <span data-ttu-id="5c9fa-103">Para guardar un informe en un servidor de informes configurado para la integración de SharePoint, debe examinar el servidor de SharePoint y establecer una conexión con el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5c9fa-103">To save a report to a report server configured for SharePoint integration, you must browse to the SharePoint server and establish a connection to the report server.</span></span> <span data-ttu-id="5c9fa-104">En la definición de informe, todas las referencias a los elementos relacionados con el informe deben utilizar valores que sean específicos de un servidor de informes de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5c9fa-104">In the report definition, all references to items related to the report must use values that are specific to a SharePoint report server.</span></span> <span data-ttu-id="5c9fa-105">Los elementos relacionados incluyen subinformes, informes detallados y recursos como imágenes basadas en web.</span><span class="sxs-lookup"><span data-stu-id="5c9fa-105">Related items include subreports, drillthrough reports, and resources such as Web-based images.</span></span> <span data-ttu-id="5c9fa-106">Para más información, vea [Especificar las rutas de acceso a los elementos externos &#40;Generador de informes y SSRS&#41;](../report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5c9fa-106">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](../report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="5c9fa-107">Debe disponer del permiso **Miembro** o **Propietario** en el sitio de SharePoint para establecer las propiedades en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5c9fa-107">You must have **Member** or **Owner** permission on the SharePoint site to set the properties on the project.</span></span>  
  
### <a name="to-save-a-report-to-a-sharepoint-site"></a><span data-ttu-id="5c9fa-108">Guardar un informe en un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="5c9fa-108">To save a report to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="5c9fa-109">Desde el botón Generador de informes, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5c9fa-109">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="5c9fa-110">Se abre el cuadro de diálogo **Guardar como** _\<Report Item>_ .</span><span class="sxs-lookup"><span data-stu-id="5c9fa-110">The **Save As**_\<Report Item>_ dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5c9fa-111">Si vuelve a guardar un informe, automáticamente se guarda en su ubicación anterior.</span><span class="sxs-lookup"><span data-stu-id="5c9fa-111">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="5c9fa-112">Utilice la opción **Guardar como** para cambiar la ubicación.</span><span class="sxs-lookup"><span data-stu-id="5c9fa-112">Use the **Save As** option to change location.</span></span>  
  
2.  <span data-ttu-id="5c9fa-113">Si lo desea, puede hacer clic en **Sitios y servidores recientes** para mostrar una lista de servidores de informes y sitios de SharePoint utilizados recientemente.</span><span class="sxs-lookup"><span data-stu-id="5c9fa-113">Optionally, click **Recent Sites and Servers** to show a list of recently used report servers and SharePoint sites.</span></span>  
  
3.  <span data-ttu-id="5c9fa-114">Vaya al sitio de SharePoint y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5c9fa-114">Browse to the SharePoint site, and then click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5c9fa-115">Si deja un informe cambiado durante más de diez horas sin guardarlo, se desconecta del servidor sin guardarse.</span><span class="sxs-lookup"><span data-stu-id="5c9fa-115">If you leave a changed report for more than 10 hours without saving it, it is disconnected from the server without being saved.</span></span> <span data-ttu-id="5c9fa-116">Si ocurre esto, en la barra de estado inferior derecha, haga clic en **Desconectar**y, después, en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="5c9fa-116">If that happens, in the lower-right status bar, click **Disconnect**, and then click **Connect**.</span></span> <span data-ttu-id="5c9fa-117">El servidor más reciente estará en la lista de servidores disponibles.</span><span class="sxs-lookup"><span data-stu-id="5c9fa-117">The most recent server will be in the list of available servers.</span></span> <span data-ttu-id="5c9fa-118">Selecciónelo y el informe volverá a conectarse.</span><span class="sxs-lookup"><span data-stu-id="5c9fa-118">Select it and the report will reconnect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c9fa-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c9fa-119">See Also</span></span>  
 [<span data-ttu-id="5c9fa-120">Buscar, ver y administrar informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5c9fa-120">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
