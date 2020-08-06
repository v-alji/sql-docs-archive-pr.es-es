---
title: Exportar una base de conocimiento a un archivo .dqs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a324ead5-c8aa-4e26-abe3-ef415add00f8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 81dfc8e7f20fae9dacd521595d101be3117a6794
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669844"
---
# <a name="export-a-knowledge-base-to-a-dqs-file"></a><span data-ttu-id="83940-102">Exportar una base de conocimiento a un archivo .dqs</span><span class="sxs-lookup"><span data-stu-id="83940-102">Export a Knowledge Base to a .dqs File</span></span>
  <span data-ttu-id="83940-103">En este tema se describe cómo exportar una base de conocimiento completa a un archivo de datos .dqs en [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="83940-103">This topic describes how to export an entire knowledge base to a .dqs data file in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="83940-104">Puede exportar un dominio o una base de conocimiento completa a un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="83940-104">You can export a domain or an entire knowledge base to a data file.</span></span> <span data-ttu-id="83940-105">Para información sobre cómo exportar un dominio, vea [Exportar un dominio a un archivo .dqs](../../2014/data-quality-services/export-a-domain-to-a-dqs-file.md).</span><span class="sxs-lookup"><span data-stu-id="83940-105">For information about exporting a domain, see [Export a Domain to a .dqs File](../../2014/data-quality-services/export-a-domain-to-a-dqs-file.md).</span></span>  
  
 <span data-ttu-id="83940-106">Exportar una base de conocimiento a un archivo .dqs e importarlo después como otra base de conocimiento simplifica el proceso de generación del conocimiento, lo que permite ahorrar tiempo y esfuerzo.</span><span class="sxs-lookup"><span data-stu-id="83940-106">Exporting a knowledge base to a .dqs file, and then importing it as another knowledge base simplifies the knowledge generation process, saving time and effort.</span></span> <span data-ttu-id="83940-107">Le permite compartir con los demás una base de conocimiento y su conocimiento.</span><span class="sxs-lookup"><span data-stu-id="83940-107">It enables you to share a knowledge base and its knowledge with others.</span></span> <span data-ttu-id="83940-108">El archivo .dqs contendrá toda la información de la base de conocimiento, incluido los dominios y la directiva de coincidencia, salvo la información de datos de referencia adjunta.</span><span class="sxs-lookup"><span data-stu-id="83940-108">The .dqs file will contain all knowledge base information, including domains and the matching policy, except for the attached reference data information.</span></span> <span data-ttu-id="83940-109">Debe volver a adjuntar los dominios necesarios a los servicios de datos de referencia adecuados, si es necesario, después de importar el archivo .dqs.</span><span class="sxs-lookup"><span data-stu-id="83940-109">You must attach the required domains to appropriate reference data services again, if required, after importing the .dqs file.</span></span> <span data-ttu-id="83940-110">Se exportan tanto los datos publicados como los no publicados en una base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="83940-110">Both published and unpublished data in a knowledge base is exported.</span></span>  
  
 <span data-ttu-id="83940-111">El archivo de datos .dqs creado por el proceso de exportación se cifra, por lo que no se puede ver el contenido.</span><span class="sxs-lookup"><span data-stu-id="83940-111">The .dqs data file created by the export process is encrypted, so the contents cannot be viewed.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="83940-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="83940-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="83940-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="83940-113">Prerequisites</span></span>  
 <span data-ttu-id="83940-114">Para exportar una base de conocimiento a un archivo de datos .dqs, debe haber creado y abierto la base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="83940-114">To export a knowledge base to a .dqs data file, you must have created and opened a knowledge base.</span></span> <span data-ttu-id="83940-115">No es necesario que disponga de un archivo .dqs; se creará uno automáticamente.</span><span class="sxs-lookup"><span data-stu-id="83940-115">You do not need to have a .dqs file to export into; one will be created for you.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="83940-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="83940-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="83940-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="83940-117">Permissions</span></span>  
 <span data-ttu-id="83940-118">Debe disponer del rol dqs_kb_editor o dqs_administrator en la base de datos DQS_MAIN para exportar una base de conocimiento a un archivo de datos .dqs.</span><span class="sxs-lookup"><span data-stu-id="83940-118">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to export a knowledge base to a .dqs data file.</span></span>  
  
##  <a name="export-a-knowledge-base-to-a-dqs-file"></a><a name="Export"></a><span data-ttu-id="83940-119">Exportar una base de conocimiento a un archivo. DQS</span><span class="sxs-lookup"><span data-stu-id="83940-119">Export a knowledge base to a .dqs file</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="83940-120">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="83940-120">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="83940-121">En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , abra una base de conocimiento en la actividad Administración de dominios.</span><span class="sxs-lookup"><span data-stu-id="83940-121">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open a knowledge base in the Domain Management activity.</span></span>  
  
3.  <span data-ttu-id="83940-122">En la página Administración de dominios (con cualquier pestaña seleccionada), haga clic en el icono **Exportar datos de la base de conocimiento** situado encima de la lista de dominios y, a continuación, haga clic en **Exportar base de conocimiento**.</span><span class="sxs-lookup"><span data-stu-id="83940-122">In the Domain Management page (with any tab selected), click the **Export Knowledge Base data** icon above the Domain list, and then click **Export Knowledge Base**.</span></span> <span data-ttu-id="83940-123">O bien, haga clic con el botón secundario en la lista **Dominios** , mantenga el mouse sobre **Exportar**y, a continuación, haga clic en **Exportar base de conocimiento**.</span><span class="sxs-lookup"><span data-stu-id="83940-123">Alternatively, you can also right-click in the **Domain** list, hover over **Export**, and then click **Export Knowledge Base**.</span></span>  
  
4.  <span data-ttu-id="83940-124">En el cuadro de diálogo **Exportar a un archivo de datos**, desplácese a la carpeta en la que quiere guardar el archivo, asígnele un nombre o conserve el nombre de la base de conocimiento, mantenga seleccionada la opción **Archivos de datos DQS (\*.dqs)** en la lista **Guardar como tipo** y, luego, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="83940-124">In the **Export to Data File** dialog box, move to the folder that you want to save the file in, name the file or keep the knowledge base name, keep **DQS Data Files (\*.dqs)** as the **Save as** type, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="83940-125">En el cuadro de diálogo **Exportar base de conocimiento** , compruebe que la línea de estado indica que se ha completado la exportación.</span><span class="sxs-lookup"><span data-stu-id="83940-125">In the **Export Knowledge Base** dialog box, verify that the status line indicates that the export completed.</span></span> <span data-ttu-id="83940-126">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="83940-126">Click **OK**.</span></span>  
  
##  <a name="follow-up-after-exporting-a-domain-to-a-dqs-file"></a><a name="FollowUp"></a><span data-ttu-id="83940-127">Seguimiento: después de exportar un dominio a un archivo. DQS</span><span class="sxs-lookup"><span data-stu-id="83940-127">Follow Up: After Exporting a Domain to a .dqs File</span></span>  
 <span data-ttu-id="83940-128">Después de exportar una base de conocimiento a un archivo .dqs, puede importarla en el mismo [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] (con un nuevo nombre) o en otro [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83940-128">After you export a knowledge base to a .dqs file, you can import the knowledge base into the same [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] (with a new name) or into a different [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
  
