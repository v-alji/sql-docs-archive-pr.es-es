---
title: Agregar un destino mediante el Asistente de destino | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 747a0de0-3c2f-4d31-a692-7111fc0911d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd36828a7bab7fb33b86765f9f064b6406a17a9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669814"
---
# <a name="add-a-destination-using-destination-assistant"></a><span data-ttu-id="b668a-102">Agregar un destino mediante el Asistente de destinos</span><span class="sxs-lookup"><span data-stu-id="b668a-102">Add a Destination using Destination Assistant</span></span>
  <span data-ttu-id="b668a-103">En este tema se proporcionan los pasos para agregar un nuevo destino mediante el Asistente de destinos y también se muestran las opciones disponibles en el cuadro de diálogo **Agregar nuevo destino** , que verá al arrastrar y colocar el Asistente de destinos en el Diseñador SSIS.</span><span class="sxs-lookup"><span data-stu-id="b668a-103">This topic provides steps to add a new destination using the Destination Assistant and also lists the options that are available on the **Add New Destination** dialog, which you will see when you drag-drop the Destination Assistant to the SSIS Designer.</span></span>  
  
### <a name="to-use-destination-assistant-to-add-a-destination"></a><span data-ttu-id="b668a-104">Para utilizar el Asistente de destinos para agregar un destino</span><span class="sxs-lookup"><span data-stu-id="b668a-104">To use Destination Assistant to add a destination</span></span>  
  
1.  <span data-ttu-id="b668a-105">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] al que desea agregar un componente de destino.</span><span class="sxs-lookup"><span data-stu-id="b668a-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you want to add a destination component to.</span></span>  
  
2.  <span data-ttu-id="b668a-106">Arrastre el componente **Asistente de destinos** desde el cuadro de herramientas de SSIS hasta la pestaña **Flujo de datos** . Debe ver el cuadro de diálogo **Agregar nuevo destino** .</span><span class="sxs-lookup"><span data-stu-id="b668a-106">Drag the **Destination Assistant** component from the SSIS Toolbox to the **Data Flow** tab. You should see the **Add New Destination** dialog box.</span></span> <span data-ttu-id="b668a-107">En la siguiente sección se proporcionan detalles sobre las opciones disponibles en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b668a-107">The next section provides you details about the options available in the dialog box.</span></span>  
  
3.  <span data-ttu-id="b668a-108">Seleccione el tipo de destino en la lista **Tipos** .</span><span class="sxs-lookup"><span data-stu-id="b668a-108">Select the type of the destination in the **Types** list.</span></span>  
  
4.  <span data-ttu-id="b668a-109">Seleccione un administrador de conexiones existente en la lista **Administradores de conexiones** o seleccione **\<New>** para crear uno.</span><span class="sxs-lookup"><span data-stu-id="b668a-109">Select an existing connection manager in the **Connection Managers** list or select **\<New>** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="b668a-110">Si selecciona un administrador de conexiones existente, haga clic **Aceptar** para cerrar el cuadro de diálogo **Agregar nuevo destino** .</span><span class="sxs-lookup"><span data-stu-id="b668a-110">If you select an existing connection manager, click **OK** to close the **Add New Destination** dialog box.</span></span> <span data-ttu-id="b668a-111">Debería ver el destino y los administradores de conexiones agregados al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="b668a-111">You should see the destination and connection managers added to the data flow.</span></span>  
  
6.  <span data-ttu-id="b668a-112">Si hace clic en **\<New>** para crear un nuevo administrador de conexiones, aparecerá el cuadro de diálogo **Administrador de conexión**, que permite especificar parámetros para la conexión.</span><span class="sxs-lookup"><span data-stu-id="b668a-112">If you click **\<New>** to create a new connection manager, you should see a **Connection Manager** dialog box, which lets you specify parameters for the connection.</span></span> <span data-ttu-id="b668a-113">Después de que finalice la creación del nuevo administrador de conexiones, verá el destino y el administrador de conexiones en el Diseñador SSIS.</span><span class="sxs-lookup"><span data-stu-id="b668a-113">After you are done with creating the new connection manager, you will see the destination and the connection manager in SSIS Designer.</span></span>  
  
  
