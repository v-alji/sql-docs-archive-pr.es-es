---
title: Agregar un origen mediante el Asistente de orígenes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5e850b7c-4b89-42ad-b0a6-d63ac7cc9568
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b58b10508765580e0cffe9bd62099f3e2d69863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672256"
---
# <a name="add-a-source-using-source-assistant"></a><span data-ttu-id="87000-102">Agregar un origen mediante el Asistente de orígenes</span><span class="sxs-lookup"><span data-stu-id="87000-102">Add a Source using Source Assistant</span></span>
  <span data-ttu-id="87000-103">En este tema se proporcionan los pasos para agregar un nuevo origen con el Asistente de orígenes y también se muestran las opciones disponibles en el cuadro de diálogo **Agregar nuevo origen** , que verá al arrastrar y colocar el Asistente de orígenes al Diseñador SSIS.</span><span class="sxs-lookup"><span data-stu-id="87000-103">This topic provides steps to add a new source using the Source Assistant and also lists the options that are available on the **Add New Source** dialog, which you will see when you drag-drop the Source Assistant to the SSIS Designer.</span></span>  
  
### <a name="to-use-source-assistant-to-add-a-source"></a><span data-ttu-id="87000-104">Para utilizar el Asistente de orígenes para agregar un origen</span><span class="sxs-lookup"><span data-stu-id="87000-104">To use Source Assistant to add a source</span></span>  
  
1.  <span data-ttu-id="87000-105">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] al que desea agregar un componente de origen.</span><span class="sxs-lookup"><span data-stu-id="87000-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you want to add a source component to.</span></span>  
  
2.  <span data-ttu-id="87000-106">Arrastre el componente **Asistente de orígenes** desde el cuadro de herramientas de SSIS hasta la pestaña **Flujo de datos** . Debe ver el cuadro de diálogo **Agregar nuevo origen** .</span><span class="sxs-lookup"><span data-stu-id="87000-106">Drag the **Source Assistant** component from the SSIS Toolbox to the **Data Flow** tab. You should see the **Add New Source** dialog box.</span></span> <span data-ttu-id="87000-107">En la siguiente sección se proporcionan detalles sobre las opciones disponibles en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="87000-107">The next section provides you details about the options available in the dialog box.</span></span>  
  
3.  <span data-ttu-id="87000-108">Seleccione el tipo de destino en la lista **Tipos** .</span><span class="sxs-lookup"><span data-stu-id="87000-108">Select the type of the destination in the **Types** list.</span></span>  
  
4.  <span data-ttu-id="87000-109">Seleccione un administrador de conexiones existente en la lista **Administradores de conexiones** o seleccione **\<New>** para crear uno.</span><span class="sxs-lookup"><span data-stu-id="87000-109">Select an existing connection manager in the **Connection Managers** list or select **\<New>** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="87000-110">Si selecciona un administrador de conexiones existente, haga clic **Aceptar** para cerrar el cuadro de diálogo **Agregar nuevo destino** .</span><span class="sxs-lookup"><span data-stu-id="87000-110">If you select an existing connection manager, click **OK** to close the **Add New Destination** dialog box.</span></span> <span data-ttu-id="87000-111">Debería ver el destino y los administradores de conexiones agregados al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="87000-111">You should see the destination and connection managers added to the data flow.</span></span>  
  
6.  <span data-ttu-id="87000-112">Si hace clic en **\<New>** para crear un nuevo administrador de conexiones, aparecerá el cuadro de diálogo **Administrador de conexión**, que permite especificar parámetros para la conexión.</span><span class="sxs-lookup"><span data-stu-id="87000-112">If you click **\<New>** to create a new connection manager, you should see a **Connection Manager** dialog box, which lets you specify parameters for the connection.</span></span> <span data-ttu-id="87000-113">Después de que finalice la creación del nuevo administrador de conexiones, verá el destino y el administrador de conexiones en el Diseñador SSIS.</span><span class="sxs-lookup"><span data-stu-id="87000-113">After you are done with creating the new connection manager, you will see the destination and the connection manager in SSIS Designer.</span></span>  
  
  
