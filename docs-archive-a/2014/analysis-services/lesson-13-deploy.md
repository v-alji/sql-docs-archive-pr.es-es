---
title: 'Lección 14: implementar | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 24863a8a-9017-415a-a97b-fbac76ed0675
author: minewiskan
ms.author: owend
ms.openlocfilehash: c1a55960a0c33a386d978f3c15e489ed7bd861ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662300"
---
# <a name="lesson-14-deploy"></a><span data-ttu-id="9cb06-102">Lección 14: Implementar</span><span class="sxs-lookup"><span data-stu-id="9cb06-102">Lesson 14: Deploy</span></span>
  <span data-ttu-id="9cb06-103">En esta lección, configurará propiedades de implementación, especificará una instancia del servidor de implementación de Analysis Services que se ejecute en modo tabular y asignará un nombre al modelo que va a implementar.</span><span class="sxs-lookup"><span data-stu-id="9cb06-103">In this lesson, you will configure deployment properties; specifying a deployment server instance of Analysis Services running in Tabular mode, and a name for the model you deploy.</span></span> <span data-ttu-id="9cb06-104">A continuación, implementará el modelo en esa instancia.</span><span class="sxs-lookup"><span data-stu-id="9cb06-104">You will then deploy the model to that instance.</span></span> <span data-ttu-id="9cb06-105">Una vez implementado, los usuarios podrán conectarse al modelo mediante una aplicación cliente de informes.</span><span class="sxs-lookup"><span data-stu-id="9cb06-105">After it is deployed, users can connect to the model by using a reporting client application.</span></span> <span data-ttu-id="9cb06-106">Para obtener más información, vea [Implementación de soluciones de modelos tabulares &#40;SSAS tabular&#41;](tabular-models/tabular-model-solution-deployment-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="9cb06-106">To learn more, see [Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-models/tabular-model-solution-deployment-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="9cb06-107">Tiempo estimado para completar esta lección: **5 minutos**</span><span class="sxs-lookup"><span data-stu-id="9cb06-107">Estimated time to complete this lesson: **5 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9cb06-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9cb06-108">Prerequisites</span></span>  
 <span data-ttu-id="9cb06-109">Este tema forma parte de un tutorial de modelado tabular, que se debe completar en orden.</span><span class="sxs-lookup"><span data-stu-id="9cb06-109">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="9cb06-110">Antes de realizar las tareas de esta lección, debe haber completado la lección anterior: [Lección 13: Analizar en Excel](lesson-12-analyze-in-excel.md).</span><span class="sxs-lookup"><span data-stu-id="9cb06-110">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 13: Analyze in Excel](lesson-12-analyze-in-excel.md).</span></span>  
  
## <a name="deploy-the-model"></a><span data-ttu-id="9cb06-111">Implementar el modelo</span><span class="sxs-lookup"><span data-stu-id="9cb06-111">Deploy the Model</span></span>  
  
#### <a name="to-configure-deployment-properties"></a><span data-ttu-id="9cb06-112">Para configurar las propiedades de implementación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9cb06-112">To configure deployment properties</span></span>  
  
1.  <span data-ttu-id="9cb06-113">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en **Explorador de soluciones**, haga clic con el botón derecho en **Modelo tabular de ventas por Internet de Adventure Works** y, en el menú contextual, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9cb06-113">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in **Solution Explorer**, right-click on the **Adventure Works Internet Sales Tabular Model** project, and then in the context menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="9cb06-114">En el cuadro de diálogo **Páginas de propiedades del modelo tabular de ventas por Internet de AW** , bajo **Servidor de implementación**, en la propiedad **Server** , escriba el nombre de una instancia de Analysis Services que se ejecute en modo Tabular.</span><span class="sxs-lookup"><span data-stu-id="9cb06-114">In the **AW Internet Sales Tabular Model Property Pages** dialog box, under **Deployment Server**, in the **Server** property, type the name of an Analysis Services instance running in Tabular mode.</span></span> <span data-ttu-id="9cb06-115">Esta será la instancia en la que se implementará el modelo.</span><span class="sxs-lookup"><span data-stu-id="9cb06-115">This will be the instance your model will be deployed to.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9cb06-116">Debe tener permisos de administrador en una instancia de Analysis Services remota para poder implementarlo.</span><span class="sxs-lookup"><span data-stu-id="9cb06-116">You must have Administrator permissions on a remote Analysis Services instance in-order to deploy to it.</span></span>  
  
3.  <span data-ttu-id="9cb06-117">Compruebe que la propiedad **modo de consulta** está establecida en **in-memory**.</span><span class="sxs-lookup"><span data-stu-id="9cb06-117">Verify the **Query Mode** property is set to **In-Memory**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9cb06-118">El modelo creado mediante este tutorial no admite el modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="9cb06-118">The model created by using this tutorial is not supported in DirectQuery mode.</span></span>  
  
4.  <span data-ttu-id="9cb06-119">En la propiedad **Database** , escriba `Adventure Works Internet Sales Model` .</span><span class="sxs-lookup"><span data-stu-id="9cb06-119">In the **Database** property, type `Adventure Works Internet Sales Model`.</span></span>  
  
5.  <span data-ttu-id="9cb06-120">En la propiedad nombre del **cubo** , escriba `Adventure Works Internet Sales Model` .</span><span class="sxs-lookup"><span data-stu-id="9cb06-120">In the **Cube** Name property, type `Adventure Works Internet Sales Model`.</span></span>  
  
6.  <span data-ttu-id="9cb06-121">Compruebe sus selecciones y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9cb06-121">Verify your selections and then click **OK**.</span></span>  
  
#### <a name="to-deploy-the-adventure-works-internet-sales-tabular-model"></a><span data-ttu-id="9cb06-122">Para implementar el modelo tabular Ventas por Internet de Adventure Works</span><span class="sxs-lookup"><span data-stu-id="9cb06-122">To deploy the Adventure Works Internet Sales tabular model</span></span>  
  
1.  <span data-ttu-id="9cb06-123">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], haga clic en el menú **Generar** y, después, haga clic en **Implementar modelo tabular de ventas por Internet de AW**.</span><span class="sxs-lookup"><span data-stu-id="9cb06-123">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Build** menu, and then click **Deploy AW Internet Sales Tabular Model**.</span></span>  
  
     <span data-ttu-id="9cb06-124">Aparece el cuadro de diálogo Implementar en el que se muestra el estado de implementación de los metadatos y las tablas incluidas en el modelo.</span><span class="sxs-lookup"><span data-stu-id="9cb06-124">The Deploy dialog box appears and displays the deployment status of the metadata as well as each table included in the model.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="9cb06-125">Conclusión</span><span class="sxs-lookup"><span data-stu-id="9cb06-125">Conclusion</span></span>  
 <span data-ttu-id="9cb06-126">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="9cb06-126">Congratulations!</span></span> <span data-ttu-id="9cb06-127">Ha terminado de crear e implementar su primer modelo tabular de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9cb06-127">You are finished authoring and deploying your first Analysis Services tabular model.</span></span> <span data-ttu-id="9cb06-128">Este tutorial le ha ayudado a completar las tareas más comunes en la creación de un modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="9cb06-128">This tutorial has helped guide you through completing the most common tasks in creating a tabular model.</span></span> <span data-ttu-id="9cb06-129">Ahora que su modelo Ventas por Internet de Adventure Works está implementado, puede utilizar el SQL Server Management Studio para administrarlo, crear scripts de proceso y realizar un plan de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9cb06-129">Now that your Adventure Works Internet Sales Model is deployed, you can use SQL Server Management Studio to manage the model; create process scripts and a backup plan.</span></span> <span data-ttu-id="9cb06-130">Los usuarios pueden conectarse al modelo mediante una aplicación cliente de informes como Microsoft Excel o [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cb06-130">Users can connect to the model using a reporting client application such as Microsoft Excel or [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)].</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="9cb06-131">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9cb06-131">Additional Resources</span></span>  
 <span data-ttu-id="9cb06-132">Para obtener más información sobre las propiedades de modelo tabular que admiten informes de [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)], vea [Propiedades de informes de Power View &#40;SSAS tabular&#41;](tabular-models/properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="9cb06-132">To learn more about tabular model properties that support [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)] reports, see [Power View Reporting Properties &#40;SSAS Tabular&#41;](tabular-models/properties-ssas-tabular.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb06-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9cb06-133">See Also</span></span>  
 <span data-ttu-id="9cb06-134">[Modo DirectQuery &#40;&#41;tabular de SSAS](tabular-models/directquery-mode-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="9cb06-134">[DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span></span>  
 <span data-ttu-id="9cb06-135">[Configurar las propiedades predeterminadas de modelado de datos y de implementación &#40;SSAS tabular&#41;](tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="9cb06-135">[Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;](tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="9cb06-136">Bases de datos de modelo tabular &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="9cb06-136">Tabular Model Databases &#40;SSAS Tabular&#41;</span></span>](tabular-models/tabular-model-databases-ssas-tabular.md)  
  
  
