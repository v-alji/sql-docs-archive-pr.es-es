---
title: Descripción del código XML de flujo de trabajo personalizado (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: e267e5f4-38bb-466d-82e8-871eabeec07e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 77906426ddb901ec422367bf30aabef2e532ad06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678219"
---
# <a name="custom-workflow-xml-description-master-data-services"></a><span data-ttu-id="1ac2d-102">Descripción del código XML de flujo de trabajo personalizado (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="1ac2d-102">Custom Workflow XML Description (Master Data Services)</span></span>
  <span data-ttu-id="1ac2d-103">En [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] , se llama al método [Microsoft. MasterDataServices. WorkflowTypeExtender. IWorkflowTypeExtender. StartWorkflow \*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) mediante SQL Server servicio de integración de flujos de trabajo de MDS cuando se inicia un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1ac2d-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)], the [Microsoft.MasterDataServices.WorkflowTypeExtender.IWorkflowTypeExtender.StartWorkflow\*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) method is called by SQL Server MDS Workflow Integration Service when a workflow starts.</span></span> <span data-ttu-id="1ac2d-104">Este método recibe los metadatos y los datos del elemento que desencadenó la regla de negocio del flujo de trabajo como un bloque de XML.</span><span class="sxs-lookup"><span data-stu-id="1ac2d-104">This method receives metadata and data about the item that triggered the workflow business rule as a block of XML.</span></span> <span data-ttu-id="1ac2d-105">Para ver un código de ejemplo que implemente un controlador de flujo de trabajo, vea [Ejemplo de flujo de trabajo personalizado &#40;Master Data Services&#41;](create-a-custom-workflow-example.md).</span><span class="sxs-lookup"><span data-stu-id="1ac2d-105">For example code that implements a workflow handler, see [Custom Workflow Example &#40;Master Data Services&#41;](create-a-custom-workflow-example.md).</span></span>  
  
 <span data-ttu-id="1ac2d-106">El ejemplo siguiente es un ejemplo del código XML que se envía al controlador del flujo de trabajo:</span><span class="sxs-lookup"><span data-stu-id="1ac2d-106">The following example shows what the XML that is sent to the workflow handler might look like:</span></span>  
  
```scr  
<ExternalAction>  
  <Type>TEST</Type>  
  <SendData>1</SendData>  
  <Server_URL>This is my test!</Server_URL>  
  <Action_ID>Test Workflow</Action_ID>  
  <Model_ID>5</Model_ID>  
  <Model_Name>Customer</Model_Name>  
  <Entity_ID>34</Entity_ID>  
  <Entity_Name>Customer</Entity_Name>  
  <Version_ID>8</Version_ID>  
  <MemberType_ID>1</MemberType_ID>  
  <Member_ID>12</Member_ID>  
  <MemberData>  
    <ID>12</ID>  
    <Version_ID>8</Version_ID>  
    <ValidationStatus_ID>3</ValidationStatus_ID>  
    <ChangeTrackingMask>0</ChangeTrackingMask>  
    <EnterDTM>2011-02-25T20:16:36.650</EnterDTM>  
    <EnterUserID>2</EnterUserID>  
    <EnterUserName>MyUserName</EnterUserName>  
    <EnterUserMuid>EEF91D48-B673-4D83-B95F-5A363C11DE91</EnterUserMuid>  
    <EnterVersionId>8</EnterVersionId>  
    <EnterVersionName>VERSION_1</EnterVersionName>  
    <EnterVersionMuid>52B788C2-2750-4651-9DB0-2CB05A88AA5A</EnterVersionMuid>  
    <LastChgDTM>2011-02-25T20:16:36.650</LastChgDTM>  
    <LastChgUserID>2</LastChgUserID>  
    <LastChgUserName>MyUserName</LastChgUserName>  
    <LastChgUserMuid>EEF91D48-B673-4D83-B95F-5A363C11DE91</LastChgUserMuid>  
    <LastChgVersionId>8</LastChgVersionId>  
    <LastChgVersionName>VERSION_1</LastChgVersionName>  
    <LastChgVersionMuid>52B788C2-2750-4651-9DB0-2CB05A88AA5A</LastChgVersionMuid>  
    <Name>Test Customer</Name>  
    <Code>TC</Code>  
  </MemberData>  
</ExternalAction>  
```  
  
 <span data-ttu-id="1ac2d-107">En la tabla siguiente se describen algunas de las etiquetas incluidas en este XML:</span><span class="sxs-lookup"><span data-stu-id="1ac2d-107">The following table describes some of the tags contained in this XML:</span></span>  
  
|<span data-ttu-id="1ac2d-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="1ac2d-108">Tag</span></span>|<span data-ttu-id="1ac2d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ac2d-109">Description</span></span>|  
|---------|-----------------|  
|\<Type>|<span data-ttu-id="1ac2d-110">El texto que especificó en el cuadro de texto **Tipo de flujo de trabajo** de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] para identificar el ensamblado del flujo de trabajo personalizado que se debe cargar.</span><span class="sxs-lookup"><span data-stu-id="1ac2d-110">The text you entered in the **Workflow type** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] to identify which custom workflow assembly to load.</span></span>|  
|\<SendData>|<span data-ttu-id="1ac2d-111">Valor booleano controlado por la casilla **Incluir datos de miembro en el mensaje** de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ac2d-111">A Boolean value controlled by the **Include member data in the message** checkbox in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="1ac2d-112">Un valor de 1 significa que \<MemberData> se envía la sección; de lo contrario, \<MemberData> no se envía la sección.</span><span class="sxs-lookup"><span data-stu-id="1ac2d-112">A value of 1 means that the \<MemberData> section is sent; otherwise the \<MemberData> section is not sent.</span></span>|  
|<span data-ttu-id="1ac2d-113"><Server_URL></span><span class="sxs-lookup"><span data-stu-id="1ac2d-113"><Server_URL></span></span>|<span data-ttu-id="1ac2d-114">El texto que especificó en el cuadro de texto **Sitio de flujo de trabajo** de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ac2d-114">The text you entered in the **Workflow site** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>|  
|<span data-ttu-id="1ac2d-115"><Action_ID></span><span class="sxs-lookup"><span data-stu-id="1ac2d-115"><Action_ID></span></span>|<span data-ttu-id="1ac2d-116">El texto que especificó en el cuadro de texto **Nombre de flujo de trabajo** de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ac2d-116">The text you entered in the **Workflow name** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>|  
|\<MemberData>|<span data-ttu-id="1ac2d-117">Contiene los datos del miembro que desencadenó la acción del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1ac2d-117">Contains the data of the member that triggered the workflow action.</span></span> <span data-ttu-id="1ac2d-118">Solo se incluye si el valor de \<SendData> es 1.</span><span class="sxs-lookup"><span data-stu-id="1ac2d-118">This is included only if the value of \<SendData> is 1.</span></span>|  
|\<Enter*xxx*>|<span data-ttu-id="1ac2d-119">Este conjunto de etiquetas contiene metadatos sobre la creación del miembro, por ejemplo, cuándo se creó y quién lo creó.</span><span class="sxs-lookup"><span data-stu-id="1ac2d-119">This set of tags contains metadata about the creation of the member, such as when it was created and who created it.</span></span>|  
|\<LastChg*xxx*>|<span data-ttu-id="1ac2d-120">Este conjunto de etiquetas contiene metadatos sobre el último cambio realizado en el miembro, como cuándo se realizó el cambio y quién lo hizo.</span><span class="sxs-lookup"><span data-stu-id="1ac2d-120">This set of tags contains metadata about the last change made to the member, such as when the change was made and who made it.</span></span>|  
|\<Name>|<span data-ttu-id="1ac2d-121">Se cambió el primer atributo del miembro.</span><span class="sxs-lookup"><span data-stu-id="1ac2d-121">The first attribute of the member that was changed.</span></span> <span data-ttu-id="1ac2d-122">Este miembro de ejemplo contiene únicamente los atributos Name y Code.</span><span class="sxs-lookup"><span data-stu-id="1ac2d-122">This example member contains only Name and Code attributes.</span></span>|  
|\<Code>|<span data-ttu-id="1ac2d-123">Se cambió el siguiente atributo del miembro.</span><span class="sxs-lookup"><span data-stu-id="1ac2d-123">The next attribute of the member that was changed.</span></span> <span data-ttu-id="1ac2d-124">Si este miembro de ejemplo contuviera más atributos, se incluirían detrás de este.</span><span class="sxs-lookup"><span data-stu-id="1ac2d-124">If this example member contained more attributes, they would follow this one.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ac2d-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ac2d-125">See Also</span></span>  
 <span data-ttu-id="1ac2d-126">[Crear un flujo de trabajo personalizado &#40;Master Data Services&#41;](create-a-custom-workflow-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="1ac2d-126">[Create a Custom Workflow &#40;Master Data Services&#41;](create-a-custom-workflow-master-data-services.md) </span></span>  
 [<span data-ttu-id="1ac2d-127">Ejemplo de flujo de trabajo personalizado &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1ac2d-127">Custom Workflow Example &#40;Master Data Services&#41;</span></span>](create-a-custom-workflow-example.md)  
  
  
