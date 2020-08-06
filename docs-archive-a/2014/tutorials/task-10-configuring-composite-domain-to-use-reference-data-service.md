---
title: 'Tarea 10: configuración de un dominio compuesto para usar el servicio de datos de referencia | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 752eefde-8b87-4f54-878e-9963ccbadc8e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d70966b4cde110540bf5008eda4e3151fe32f28d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751605"
---
# <a name="task-10-configuring-composite-domain-to-use-reference-data-service"></a><span data-ttu-id="c1a77-102">Tarea 10: Configuración de un dominio compuesto para usar un servicio de datos de referencia</span><span class="sxs-lookup"><span data-stu-id="c1a77-102">Task 10: Configuring Composite Domain to Use Reference Data Service</span></span>
  <span data-ttu-id="c1a77-103">En esta tarea, configurará el dominio compuesto **validación de direcciones** para que use el servicio **Melissa Data-Address check** .</span><span class="sxs-lookup"><span data-stu-id="c1a77-103">In this task, you configure the **Address Validation** composite domain to use the **Melissa Data - Address Check** service.</span></span> <span data-ttu-id="c1a77-104">En tiempo de ejecución, durante la actividad de limpieza, DQS pasa los valores de dominios del dominio Validación de direcciones al servicio para su limpieza.</span><span class="sxs-lookup"><span data-stu-id="c1a77-104">At runtime, during cleansing activity, DQS passes the values of domains in the Address Validation domain to the service for cleansing.</span></span> <span data-ttu-id="c1a77-105">Para obtener más información [, vea asignar dominio o compuesto de dominio a datos de referencia](https://msdn.microsoft.com/library/hh213030.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c1a77-105">See [Map Domain/Composite Domain to Reference Data](https://msdn.microsoft.com/library/hh213030.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="c1a77-106">En la Página principal del **cliente DQS**, haga clic en **proveedores (administración de dominios)** en **bases de conocimiento recientes** para iniciar la página **Administración de dominios** .</span><span class="sxs-lookup"><span data-stu-id="c1a77-106">In the main page of **DQS Client**, click **Suppliers (Domain Management)** under **Recent Knowledge Bases** to launch the **Domain Management** page.</span></span>  
  
2.  <span data-ttu-id="c1a77-107">Seleccione el dominio compuesto **validación de direcciones** en la **lista de dominios**.</span><span class="sxs-lookup"><span data-stu-id="c1a77-107">Select the **Address Validation** composite domain in the **list of domains**.</span></span>  
  
3.  <span data-ttu-id="c1a77-108">En el panel derecho, cambie a la pestaña **datos de referencia** .</span><span class="sxs-lookup"><span data-stu-id="c1a77-108">In the right pane, switch to the **Reference Data** tab.</span></span>  
  
     <span data-ttu-id="c1a77-109">![Pestaña de datos de referencia](../../2014/tutorials/media/et-configuringcdtouserds-01.jpg "Pestaña de datos de referencia")</span><span class="sxs-lookup"><span data-stu-id="c1a77-109">![Reference Data Tab](../../2014/tutorials/media/et-configuringcdtouserds-01.jpg "Reference Data Tab")</span></span>  
  
4.  <span data-ttu-id="c1a77-110">Haga clic en el botón **examinar** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="c1a77-110">Click **Browse** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="c1a77-111">En el cuadro de diálogo **Catálogo de proveedores de datos de referencia en línea** **, active la casilla situada** junto a **Melissa Data-Address check**.</span><span class="sxs-lookup"><span data-stu-id="c1a77-111">On the **Online Reference Data Providers Catalog** dialog box, select **check box** next to **Melissa Data - Address Check**.</span></span>  
  
     <span data-ttu-id="c1a77-112">![Seleccionar Melissa Data - Address Check](../../2014/tutorials/media/et-configuringcdtouserds-02.jpg "Seleccionar Melissa Data - Address Check")</span><span class="sxs-lookup"><span data-stu-id="c1a77-112">![Select Melissa Data - Address Check](../../2014/tutorials/media/et-configuringcdtouserds-02.jpg "Select Melissa Data - Address Check")</span></span>  
  
6.  <span data-ttu-id="c1a77-113">En el panel derecho, en la sección **esquema** , asigne dominio de **línea de dirección** al elemento de esquema de línea de **dirección (M)** mediante la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c1a77-113">In the right pane, in the **Schema** section, map **Address Line** domain to the **Address Line (M)** schema item by using the drop-down list.</span></span>  
  
     <span data-ttu-id="c1a77-114">![Asignar elemento de esquema RDS a dominio](../../2014/tutorials/media/et-configuringcdtouserds-03.jpg "Asignar elemento de esquema RDS a dominio")</span><span class="sxs-lookup"><span data-stu-id="c1a77-114">![Map RDS Schema Item to Domain](../../2014/tutorials/media/et-configuringcdtouserds-03.jpg "Map RDS Schema Item to Domain")</span></span>  
  
7.  <span data-ttu-id="c1a77-115">Haga clic en el botón **Agregar entrada de esquema (+)** de la barra de herramientas para crear una entrada en la lista.</span><span class="sxs-lookup"><span data-stu-id="c1a77-115">Click **Add Schema Entry (+)** button on the toolbar to create an entry in the list.</span></span>  
  
     <span data-ttu-id="c1a77-116">![Botón de barra de herramientas Agregar entrada de esquema](../../2014/tutorials/media/et-configuringcdtouserds-04.jpg "Botón de barra de herramientas Agregar entrada de esquema")</span><span class="sxs-lookup"><span data-stu-id="c1a77-116">![Add Schema Entry Toolbar Button](../../2014/tutorials/media/et-configuringcdtouserds-04.jpg "Add Schema Entry Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="c1a77-117">Asigne los dominios siguientes de DQS mediante las listas desplegables según se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="c1a77-117">Map the following DQS domains by using the drop-down lists as shown in the following picture.</span></span>  
  
     <span data-ttu-id="c1a77-118">![Asignar elementos de esquema RDS a dominios](../../2014/tutorials/media/et-configuringcdtouserds-05.jpg "Asignar elementos de esquema RDS a dominios")</span><span class="sxs-lookup"><span data-stu-id="c1a77-118">![Map RDS Schema Items to Domains](../../2014/tutorials/media/et-configuringcdtouserds-05.jpg "Map RDS Schema Items to Domains")</span></span>  
  
9. <span data-ttu-id="c1a77-119">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c1a77-119">Click **OK** to close the dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="c1a77-120">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="c1a77-120">Next Step</span></span>  
 [<span data-ttu-id="c1a77-121">Tarea 11: Publicación de la base de conocimiento</span><span class="sxs-lookup"><span data-stu-id="c1a77-121">Task 11: Publishing the Knowledge Base</span></span>](../../2014/tutorials/task-11-publishing-the-knowledge-base.md)  
  
  
