---
title: Archivos de consulta de acceso directo (complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 1ba0219a-6c40-41fa-aff9-8c8f41ef3220
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fe1bdbdadabe0e6448ed3bdc65316104fb26ba43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745352"
---
# <a name="shortcut-query-files-mds-add-in-for-excel"></a><span data-ttu-id="e5aaa-102">Archivos de consulta de acceso directo (complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="e5aaa-102">Shortcut Query Files (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="e5aaa-103">En el [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], puede usar los archivos de consulta de acceso directo para conectarse a datos usados con frecuencia y cargarlos rápidamente.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use shortcut query files to quickly connect and load frequently-used data.</span></span> <span data-ttu-id="e5aaa-104">También puede utilizarlos si desea compartir datos MDS con otros.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-104">You can also use them when you want to share MDS data with others.</span></span> <span data-ttu-id="e5aaa-105">En lugar de guardar la hoja de cálculo y enviarla por correo electrónico, debe guardar un archivo de consulta de acceso directo y enviarlo por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-105">Instead of saving the worksheet and emailing it, you should save a shortcut query file and email that instead.</span></span> <span data-ttu-id="e5aaa-106">Esto garantiza que ambos se conecten al repositorio MDS para obtener los datos más recientes.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-106">This ensures that you are both connecting to the MDS repository to get the latest data.</span></span>  
  
 <span data-ttu-id="e5aaa-107">Los archivos de consulta de acceso directo son archivos XML que contienen información acerca de:</span><span class="sxs-lookup"><span data-stu-id="e5aaa-107">Shortcut query files are XML files that contain information about:</span></span>  
  
-   <span data-ttu-id="e5aaa-108">La conexión del repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-108">The MDS repository connection.</span></span>  
  
-   <span data-ttu-id="e5aaa-109">El modelo, versión y entidad.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-109">The model, version, and entity.</span></span>  
  
-   <span data-ttu-id="e5aaa-110">Los filtros que se aplicaron cuando se creó el acceso directo.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-110">Any filters that were applied when the shortcut was created.</span></span>  
  
-   <span data-ttu-id="e5aaa-111">El orden de izquierda a derecha de las columnas cuando se creó el acceso directo.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-111">The left-to-right order of the columns when the shortcut was created.</span></span>  
  
 <span data-ttu-id="e5aaa-112">Puede guardar los archivos en una lista y elegir entre ellos cuando abra el complemento.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-112">You can save these files in a list and choose from them when you open the Add-in.</span></span> <span data-ttu-id="e5aaa-113">Puede exportarlos al equipo o a una ubicación compartida, o puede enviarlos a otros.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-113">You can export them to your computer or to a shared location, or you can send them to others.</span></span>  
  
## <a name="queryopener-application"></a><span data-ttu-id="e5aaa-114">Aplicación QueryOpener</span><span class="sxs-lookup"><span data-stu-id="e5aaa-114">QueryOpener Application</span></span>  
 <span data-ttu-id="e5aaa-115">Todos los usuarios que instalan [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] tienen instalada una aplicación denominada QueryOpener.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-115">All users who install the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] have an application called QueryOpener installed.</span></span> <span data-ttu-id="e5aaa-116">Esta aplicación se usa para abrir los archivos de consulta de acceso directo en [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5aaa-116">This application is used to open shortcut query files in the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)].</span></span> <span data-ttu-id="e5aaa-117">Si hace doble clic en un archivo de consulta de acceso directo, esta aplicación se usa automáticamente para abrir el archivo en el complemento.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-117">If you double-click a shortcut query file, this application is automatically used to open the file in the Add-in.</span></span>  
  
 <span data-ttu-id="e5aaa-118">Cuando se abre un archivo de consulta de acceso directo con esta aplicación, se le pedirá que realice una conexión "segura", lo que significa que confía en el contenido de esta ubicación.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-118">When you open a shortcut query file with this application, you are prompted to make the connection a "safe" connection, which means you trust content from this location.</span></span> <span data-ttu-id="e5aaa-119">Cada vez que se marca una conexión como segura, se agrega a una lista.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-119">Each time you mark a connection as safe, it is added to a list.</span></span> <span data-ttu-id="e5aaa-120">Si desea desactivar esta lista, abra el cuadro de diálogo **Configuración** y, en la sección **Servidores agregados a la lista segura** , haga clic en **Borrar todo**.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-120">If you want to clear this list, open the **Settings** dialog box and in the **Servers Added to Safe List** section, click **Clear All**.</span></span>  
  
 <span data-ttu-id="e5aaa-121">La ubicación predeterminada de la aplicación es *unidad*: \Archivos de Programa\microsoft SQL Server\120\Master Data Services\Excel Add-In\Microsoft.MasterDataServices.QueryOpener.exe.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-121">The default location for the application is *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Excel Add-In\Microsoft.MasterDataServices.QueryOpener.exe.</span></span>  
  
 <span data-ttu-id="e5aaa-122">Hay dos maneras de abrir los archivos de consulta de acceso directo: puede importarlos o puede hacer doble clic en ellos para que se abran automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-122">There are two ways to open shortcut query files: you can import them or you can double-click them and they are opened automatically.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="e5aaa-123">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="e5aaa-123">Related Tasks</span></span>  
  
|<span data-ttu-id="e5aaa-124">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="e5aaa-124">Task Description</span></span>|<span data-ttu-id="e5aaa-125">Tema</span><span class="sxs-lookup"><span data-stu-id="e5aaa-125">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="e5aaa-126">Guardar el contenido de la hoja de cálculo activa como un archivo de consulta de acceso directo.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-126">Save the contents of the active worksheet as a shortcut query file.</span></span>|[<span data-ttu-id="e5aaa-127">Guardar un archivo de consulta de acceso directo &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="e5aaa-127">Save a Shortcut Query File &#40;MDS Add-in for Excel&#41;</span></span>](save-a-shortcut-query-file-mds-add-in-for-excel.md)|  
|<span data-ttu-id="e5aaa-128">Enviar por correo electrónico un archivo de consulta de acceso directo que representa el contenido de la hoja de cálculo activa.</span><span class="sxs-lookup"><span data-stu-id="e5aaa-128">Email a shortcut query file that represents the contents of the active worksheet.</span></span>|[<span data-ttu-id="e5aaa-129">Enviar por correo electrónico un archivo de consulta de acceso directo &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="e5aaa-129">Email a Shortcut Query File &#40;MDS Add-in for Excel&#41;</span></span>](email-a-shortcut-query-file-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="e5aaa-130">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="e5aaa-130">Related Content</span></span>  
  
-   [<span data-ttu-id="e5aaa-131">Conexiones &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="e5aaa-131">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="e5aaa-132">Complemento Master Data Services para Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="e5aaa-132">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
-   [<span data-ttu-id="e5aaa-133">Seguridad &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e5aaa-133">Security &#40;Master Data Services&#41;</span></span>](../security-master-data-services.md)  
  
  
