---
title: Buscar cadena de procesos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f6303ea4-fbbf-4cba-bc60-828df62be8c2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2e0d3743071d018a8a82f60eeaf04fd86dec3e63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745919"
---
# <a name="look-up-process-chain"></a><span data-ttu-id="3220c-102">Buscar cadena de procesos</span><span class="sxs-lookup"><span data-stu-id="3220c-102">Look Up Process Chain</span></span>
  <span data-ttu-id="3220c-103">Use el cuadro de diálogo **Buscar cadena de procesos** para buscar una cadena de procesos que se haya definido en el sistema de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="3220c-103">Use the **Look Up Process Chain** dialog box to look up a process chain that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="3220c-104">Cuando aparezca la lista de las cadenas de procesos, seleccione la cadena que desee y el origen rellenará las opciones asociadas a los valores necesarios.</span><span class="sxs-lookup"><span data-stu-id="3220c-104">When the list of available process chains appears, select the chain that you want, and the source will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="3220c-105">El origen de SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW usa el cuadro de diálogo **Buscar cadena de procesos** .</span><span class="sxs-lookup"><span data-stu-id="3220c-105">The SAP BW source of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="3220c-106">Para obtener más información acerca del origen de SAP BW, vea [SAP BW Source](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="3220c-106">To learn more about the SAP BW source, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3220c-107">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="3220c-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="3220c-108">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="3220c-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="3220c-109">**Para abrir el cuadro de diálogo Buscar cadena de procesos**</span><span class="sxs-lookup"><span data-stu-id="3220c-109">**To open the Look Up Process Chain dialog box**</span></span>  
  
1.  <span data-ttu-id="3220c-110">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="3220c-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="3220c-111">En la pestaña **Flujo de datos** , haga doble clic en el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="3220c-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="3220c-112">En **Editor de origen de SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="3220c-112">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="3220c-113">En el cuadro del grupo **Cadena de procesos** , haga clic en **Buscar** para mostrar el cuadro de diálogo **Buscar cadena de procesos** .</span><span class="sxs-lookup"><span data-stu-id="3220c-113">In the **Process Chain** group box, click **Look up** to display the **Look Up Process Chain** dialog box.</span></span>  
  
     <span data-ttu-id="3220c-114">El cuadro de grupo **Cadena de procesos** aparece solo si el valor de **Modo de ejecución** es **P -Desencadenar cadena de procesos**.</span><span class="sxs-lookup"><span data-stu-id="3220c-114">The **Process Chain** group box appears only if the value for **Execution mode** is **P - Trigger process chain**.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="3220c-115">Opciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="3220c-115">Lookup Options</span></span>  
 <span data-ttu-id="3220c-116">En los campos de búsqueda, puede filtrar los resultados mediante el carácter comodín de asterisco (\*) o mediante una cadena parcial en combinación con el carácter comodín de asterisco.</span><span class="sxs-lookup"><span data-stu-id="3220c-116">In the lookup fields, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="3220c-117">Sin embargo, si deja un campo de búsqueda vacío, la operación de búsqueda solamente se corresponderá con cadenas vacías en ese campo.</span><span class="sxs-lookup"><span data-stu-id="3220c-117">However, if you leave a lookup field empty, the lookup operation will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="3220c-118">**Cadena de procesos**</span><span class="sxs-lookup"><span data-stu-id="3220c-118">**Process chain**</span></span>  
 <span data-ttu-id="3220c-119">Escriba el nombre de la cadena de procesos que desea buscar o un nombre parcial con el carácter comodín de asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="3220c-119">Enter the name of the process chain that you want to look up, or enter a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="3220c-120">O bien, use el carácter comodín de asterisco por sí solo para incluir todas las cadenas de procesos.</span><span class="sxs-lookup"><span data-stu-id="3220c-120">Or, use the asterisk wildcard character alone to include all process chains.</span></span>  
  
 <span data-ttu-id="3220c-121">**Buscar**</span><span class="sxs-lookup"><span data-stu-id="3220c-121">**Look up**</span></span>  
 <span data-ttu-id="3220c-122">Permite buscar cadenas de procesos coincidentes que se hayan definido en el sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="3220c-122">Look up matching process chains that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="3220c-123">Buscar resultados</span><span class="sxs-lookup"><span data-stu-id="3220c-123">Lookup Results</span></span>  
 <span data-ttu-id="3220c-124">Después de hacer clic en el botón Buscar, aparece una lista de cadenas de procesos del sistema SAP Netweaver BW en una tabla con los siguientes encabezados de columna:</span><span class="sxs-lookup"><span data-stu-id="3220c-124">After you click the Look up button, a list of the process chains in the SAP Netweaver BW system appears in a table with the following column headings:</span></span>  
  
 <span data-ttu-id="3220c-125">**Cadena de procesos**</span><span class="sxs-lookup"><span data-stu-id="3220c-125">**Process Chain**</span></span>  
 <span data-ttu-id="3220c-126">Permite mostrar el nombre de la cadena de procesos que se haya definido en el sistema de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="3220c-126">Displays the name of the process chain that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="3220c-127">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3220c-127">**Description**</span></span>  
 <span data-ttu-id="3220c-128">Permite mostrar la descripción de la cadena de procesos.</span><span class="sxs-lookup"><span data-stu-id="3220c-128">Displays the description of the process chain.</span></span>  
  
 <span data-ttu-id="3220c-129">Cuando aparezca la lista de las cadenas de procesos, seleccione la cadena que desee y el origen rellenará las opciones asociadas a los valores necesarios.</span><span class="sxs-lookup"><span data-stu-id="3220c-129">When the list of available process chains appears, select the chain that you want, and the source will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3220c-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3220c-130">See Also</span></span>  
 <span data-ttu-id="3220c-131">[Editor de origen de SAP BW &#40;página Administrador de conexiones&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="3220c-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="3220c-132">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="3220c-132">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
