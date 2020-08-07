---
title: Conectarse a un repositorio MDS (complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 8f427312-4c09-4c8b-b9f9-8b235557a74b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c1db0594f07da7ff8a78642e4b2de0eb9e507164
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745355"
---
# <a name="connect-to-an-mds-repository-mds-add-in-for-excel"></a><span data-ttu-id="8d741-102">Conectarse a un repositorio MDS (complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="8d741-102">Connect to an MDS Repository (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="8d741-103">En el [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], debe conectarse a un repositorio MDS para poder cargar o publicar datos.</span><span class="sxs-lookup"><span data-stu-id="8d741-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must connect to an MDS repository before you can load or publish data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8d741-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8d741-104">Prerequisites</span></span>  
 <span data-ttu-id="8d741-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="8d741-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="8d741-106">Debe disponer de permiso de acceso al área funcional **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="8d741-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-connect-to-an-mds-repository"></a><span data-ttu-id="8d741-107">Para conectarse a un repositorio MDS</span><span class="sxs-lookup"><span data-stu-id="8d741-107">To connect to an MDS repository</span></span>  
  
1.  <span data-ttu-id="8d741-108">En MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], en la pestaña **Datos maestros** , en el grupo **Conectar y cargar** , haga clic en la flecha situada debajo del botón **Conectar** y haga clic en **Administrar conexiones**.</span><span class="sxs-lookup"><span data-stu-id="8d741-108">In the MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], on the **Master Data** tab, in the **Connect and Load** group, click the arrow under the **Connect** button and click **Manage Connections**.</span></span>  
  
2.  <span data-ttu-id="8d741-109">En el cuadro de diálogo **Administrar conexiones** , en la sección **Nueva conexión** , haga clic en **Crear una nueva conexión**.</span><span class="sxs-lookup"><span data-stu-id="8d741-109">On the **Manage Connections** dialog box, in the **New connection** section, click **Create a new connection**.</span></span>  
  
3.  <span data-ttu-id="8d741-110">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="8d741-110">Click **New**.</span></span>  
  
4.  <span data-ttu-id="8d741-111">En el cuadro de diálogo **Agregar nueva conexión** , en el campo **Descripción** , escriba una descripción de la conexión.</span><span class="sxs-lookup"><span data-stu-id="8d741-111">On the **Add New Connection** dialog box, in the **Description** field, type a description for your connection.</span></span> <span data-ttu-id="8d741-112">Esta conexión se muestra al hacer clic en la flecha situada debajo del botón **Conectar** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="8d741-112">This connection will be displayed when you click the arrow under the **Connect** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="8d741-113">En el cuadro **Dirección del servidor MDS**, escriba la dirección URL de la aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)]; por ejemplo, http://contoso/mds.</span><span class="sxs-lookup"><span data-stu-id="8d741-113">In the **MDS server address** box, type the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, for example http://contoso/mds.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8d741-114">Asegúrese de usar el nombre del equipo; no utilice "localhost".</span><span class="sxs-lookup"><span data-stu-id="8d741-114">Ensure that you use the computer name; do not use "localhost".</span></span>  
  
6.  <span data-ttu-id="8d741-115">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d741-115">Click **OK**.</span></span> <span data-ttu-id="8d741-116">El nombre se muestra en la sección **Conexiones existentes** .</span><span class="sxs-lookup"><span data-stu-id="8d741-116">The name is displayed in the **Existing Connections** section.</span></span>  
  
7.  <span data-ttu-id="8d741-117">Opcionalmente, haga clic en **Probar** para probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="8d741-117">Optionally, click **Test** to test the connection.</span></span> <span data-ttu-id="8d741-118">Se muestra un cuadro de diálogo de confirmación o de error.</span><span class="sxs-lookup"><span data-stu-id="8d741-118">A confirmation or error dialog is displayed.</span></span> <span data-ttu-id="8d741-119">Haga clic en **Aceptar** para cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="8d741-119">Click **OK** to close it.</span></span>  
  
8.  <span data-ttu-id="8d741-120">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="8d741-120">Click **Connect**.</span></span> <span data-ttu-id="8d741-121">Se muestra el panel **Master Data Services** .</span><span class="sxs-lookup"><span data-stu-id="8d741-121">The **Master Data Services** pane is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8d741-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8d741-122">Next Steps</span></span>  
  
-   [<span data-ttu-id="8d741-123">Cargar datos de MDS en Excel</span><span class="sxs-lookup"><span data-stu-id="8d741-123">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)  
  
-   [<span data-ttu-id="8d741-124">Filtre los datos antes de cargar &#40;Complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="8d741-124">Filter Data before Loading &#40;MDS Add-in for Excel&#41;</span></span>](filter-data-before-exporting-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="8d741-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d741-125">See Also</span></span>  
 [<span data-ttu-id="8d741-126">Conexiones &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="8d741-126">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
  
