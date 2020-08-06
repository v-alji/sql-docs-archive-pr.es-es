---
title: Usar relaciones de valor en un dominio compuesto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dm.cdvaluerelations.f1
ms.assetid: 5ee468f0-8538-4620-90e8-63f466c9000e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 135934ec99fed612609e5e1b962f08bb93b98ede
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751485"
---
# <a name="use-value-relations-in-a-composite-domain"></a><span data-ttu-id="f1cf6-102">Utilizar relaciones de valor en un dominio compuesto</span><span class="sxs-lookup"><span data-stu-id="f1cf6-102">Use Value Relations in a Composite Domain</span></span>
  <span data-ttu-id="f1cf6-103">En este tema se describe cómo ver las combinaciones de valores encontradas para el dominio compuesto durante el proceso de detección de conocimiento de [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="f1cf6-103">This topic describes how to view value combinations found for the composite domain during the knowledge discovery process in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="f1cf6-104">Esta página muestra el número de repeticiones de las combinaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-104">This page shows the number of occurrences of the value combinations.</span></span> <span data-ttu-id="f1cf6-105">La administración de valores no se admite en los dominios compuestos, por lo que no se puede realizar ninguna operación con estos valores.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-105">Value management is not supported for composite domains, so you cannot perform any operations on these values.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f1cf6-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f1cf6-106">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="f1cf6-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f1cf6-107">Prerequisites</span></span>  
 <span data-ttu-id="f1cf6-108">Para ver las relaciones de valor, debe haber creado y abierto un dominio compuesto.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-108">To view value relations, you must have created and opened a composite domain.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f1cf6-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f1cf6-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f1cf6-110">Permisos</span><span class="sxs-lookup"><span data-stu-id="f1cf6-110">Permissions</span></span>  
 <span data-ttu-id="f1cf6-111">Debe disponer del rol dqs_kb_editor o dqs_administrator en la base de datos DQS_MAIN para ver las relaciones de valor de un dominio compuesto.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-111">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to view value relations in a composite domain.</span></span>  
  
##  <a name="view-value-relations"></a><a name="Use"></a><span data-ttu-id="f1cf6-112">Ver relaciones de valor</span><span class="sxs-lookup"><span data-stu-id="f1cf6-112">View Value Relations</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="f1cf6-113">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="f1cf6-113">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="f1cf6-114">En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , abra o cree una base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-114">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open or create a knowledge base.</span></span> <span data-ttu-id="f1cf6-115">Seleccione **Administración de dominios** como actividad y, a continuación, haga clic en **Abrir** o en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-115">Select **Domain Management** as the activity, and then click **Open** or **Create**.</span></span> <span data-ttu-id="f1cf6-116">Para obtener más información, consulte [Crear una base de conocimiento](../../2014/data-quality-services/create-a-knowledge-base.md) o [Abrir una base de conocimiento](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="f1cf6-116">For more information, see [Create a Knowledge Base](../../2014/data-quality-services/create-a-knowledge-base.md) or [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
3.  <span data-ttu-id="f1cf6-117">En la **Lista de dominios** de la página **Administración de dominios** , seleccione el dominio compuesto para el que desea crear una regla de dominio, o cree un nuevo dominio compuesto.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-117">From the **Domain list** on the **Domain Management** page, select the composite domain that you want to create a domain rule for, or create a new composite domain.</span></span> <span data-ttu-id="f1cf6-118">Si necesita crear un nuevo dominio, vea [Create a Composite Domain](../../2014/data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="f1cf6-118">If you have to create a new domain, see [Create a Composite Domain](../../2014/data-quality-services/create-a-composite-domain.md).</span></span>  
  
4.  <span data-ttu-id="f1cf6-119">Haga clic en la pestaña **Relaciones de valor** .</span><span class="sxs-lookup"><span data-stu-id="f1cf6-119">Click the **Value Relations** tab.</span></span>  
  
5.  <span data-ttu-id="f1cf6-120">Vea las frecuencias mostradas para cada combinación de valores.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-120">View the frequencies displayed for each value combination.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f1cf6-121">La tabla **Valor** muestra las combinaciones de valores existentes en el dominio compuesto.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-121">The **Value** table shows each combination of values that exists in the composite domain.</span></span> <span data-ttu-id="f1cf6-122">Cada uno de los valores se muestra en el dominio individual al que se aplica.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-122">Each value is shown in the single domain that it applies to.</span></span> <span data-ttu-id="f1cf6-123">La ordenación predeterminada de la tabla de relaciones es por frecuencia, pero puede hacer clic en otra columna para ordenar por dicha columna.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-123">The default sorting of the value relations table is by frequency, but you can click on another column to sort by that column.</span></span> <span data-ttu-id="f1cf6-124">Solo se muestran aquellos valores con una frecuencia mayor o igual que 20.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-124">Only those values with a frequency greater than or equal to 20 are displayed.</span></span>  
  
6.  <span data-ttu-id="f1cf6-125">No se puede cambiar ninguno de los valores de la tabla.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-125">You cannot change any of the values in the table.</span></span> <span data-ttu-id="f1cf6-126">Si ha realizado otras operaciones, haga clic en **Finalizar** para completar la actividad de administración de dominios.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-126">If you have performed other operations, click **Finish** to complete the domain management activity.</span></span> <span data-ttu-id="f1cf6-127">En caso contrario, haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-127">Otherwise, click **Cancel**.</span></span>  
  
##  <a name="follow-up-after-viewing-value-relations"></a><a name="FollowUp"></a><span data-ttu-id="f1cf6-128">Seguimiento: después de ver las relaciones de valor</span><span class="sxs-lookup"><span data-stu-id="f1cf6-128">Follow Up: After Viewing Value Relations</span></span>  
 <span data-ttu-id="f1cf6-129">Una vez vistas las relaciones de valor, puede realizar otras tareas de administración en el dominio, ejecutar la detección de conocimiento para agregar conocimiento al dominio o agregar a este una directiva de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-129">After you view value relations, you can perform other domain management tasks on the domain, you can perform knowledge discovery to add knowledge to the domain, or you can add a matching policy to the domain.</span></span> <span data-ttu-id="f1cf6-130">Para más información, vea [Realizar la detección de conocimiento](../../2014/data-quality-services/perform-knowledge-discovery.md), [Administrar un dominio](../../2014/data-quality-services/managing-a-domain.md) o [Crear una directiva de coincidencia](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f1cf6-130">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
