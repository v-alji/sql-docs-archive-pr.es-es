---
title: Instale ADO.NET Data Services para admitir las exportaciones de fuentes de distribución de datos de las listas de SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: f32527ae-f623-4e08-adfb-6d3262f5c2ac
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: fb47804daee38427f48baefdf3997edda5fb90b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670766"
---
# <a name="install-adonet-data-services-to-support-data-feed-exports-of-sharepoint-lists"></a><span data-ttu-id="52770-102">Instalar ADO.NET Data Services para admitir las exportaciones de fuentes de distribución de datos de las listas de SharePoint</span><span class="sxs-lookup"><span data-stu-id="52770-102">Install ADO.NET Data Services to support data feed exports of SharePoint lists</span></span>
  <span data-ttu-id="52770-103">ADO.NET Data Services se requiere para exportar fuentes de distribución de datos de las listas de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="52770-103">ADO.NET Data Services is required for a data feed export of SharePoint lists.</span></span> <span data-ttu-id="52770-104">SharePoint 2010 no incluye este componente en el programa instalador de requisitos previos de SharePoint, de modo que debe instalarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="52770-104">SharePoint 2010 does not include this component in the SharePoint Prerequisite Installer program, so you must install it manually.</span></span>  
  
 <span data-ttu-id="52770-105">Sin este requisito previo, obtendrá el siguiente error cuando intente usar una lista de SharePoint exportada como fuente de distribución de datos: "Por motivos de seguridad, DTD se prohíbe en este documento XML.</span><span class="sxs-lookup"><span data-stu-id="52770-105">Without this prerequisite, you will get the following error when you attempt to use a SharePoint list that was exported as a data feed: "For security reasons DTD is prohibited in this XML document.</span></span> <span data-ttu-id="52770-106">Para habilitar el procesamiento DTD, establezca la propiedad ProhibitDtd de XmlReaderSettings en false y pase los ajustes al método XmlReader.Create".</span><span class="sxs-lookup"><span data-stu-id="52770-106">To enable DTD processing set the ProhibitDtd property on XmlReaderSettings to false and pass the settings into XmlReader.Create method."</span></span>  
  
 <span data-ttu-id="52770-107">Use las siguientes instrucciones para instalar ADO.NET Data Services en cada servidor de SharePoint para el que desee permitir que las listas se exporten como fuentes de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="52770-107">Use the following instructions to install ADO.NET Data Services on every SharePoint server for which you want to allow lists to be exported as data feeds.</span></span>  
  
### <a name="download-and-install-adonet-data-services"></a><span data-ttu-id="52770-108">Descargar e instalar ADO.NET Data Services</span><span class="sxs-lookup"><span data-stu-id="52770-108">Download and install ADO.NET Data Services</span></span>  
  
1.  <span data-ttu-id="52770-109">Vaya a la documentación de los requisitos de hardware y software para SharePoint 2010, [requisitos de hardware y software (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734)</span><span class="sxs-lookup"><span data-stu-id="52770-109">Go to the hardware and software requirements documentation for SharePoint 2010, [Hardware and Software Requirements (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734)</span></span>  
  
2.  <span data-ttu-id="52770-110">En **acceso a software aplicable**, busque el vínculo de ADO.NET Data Services 3,5 que corresponda al sistema operativo que usa (windows Server 2008 SP2 o windows Server 2008 R2).</span><span class="sxs-lookup"><span data-stu-id="52770-110">In **Access to applicable software**, find the link for ADO.NET Data Services 3.5 that corresponds to the operating system you are using (either Windows Server 2008 SP2 or Windows Server 2008 R2).</span></span>  
  
3.  <span data-ttu-id="52770-111">Haga clic en el vínculo y ejecute el programa de instalación que instala el servicio.</span><span class="sxs-lookup"><span data-stu-id="52770-111">Click the link and run the setup program that installs the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52770-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52770-112">See Also</span></span>  
 [<span data-ttu-id="52770-113">Instalación de PowerPivot para SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="52770-113">PowerPivot for SharePoint 2010 Installation</span></span>](../../../2014/sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
