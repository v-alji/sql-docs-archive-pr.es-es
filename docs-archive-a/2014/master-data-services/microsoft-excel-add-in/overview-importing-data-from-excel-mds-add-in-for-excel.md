---
title: Publicación de datos (Complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: ea84a9aa-aeec-411b-ab8d-bc1b14f864a3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ab37a353469d1902394a3e2cd8060d9be82abb40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747684"
---
# <a name="publishing-data-mds-add-in-for-excel"></a><span data-ttu-id="f3433-102">Publicar datos (complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="f3433-102">Publishing Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="f3433-103">En [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], puede publicar los datos en el repositorio MDS si desea compartirlo con otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="f3433-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publish data to the MDS repository when you want to share it with other users.</span></span> <span data-ttu-id="f3433-104">En cuanto se publiquen los datos, estarán disponibles para otros usuarios del complemento para su descarga.</span><span class="sxs-lookup"><span data-stu-id="f3433-104">As soon as data is published, it is available for other users of the Add-in to download.</span></span>  
  
 <span data-ttu-id="f3433-105">Al publicar datos, todos los que haya agregado o actualizado se publican en el repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="f3433-105">When you publish data, any data you've added or updated is published to the MDS repository.</span></span> <span data-ttu-id="f3433-106">Los datos que haya eliminado no se publican y se deben eliminar por separado.</span><span class="sxs-lookup"><span data-stu-id="f3433-106">Data you've deleted is not published-you must delete data separately.</span></span> <span data-ttu-id="f3433-107">Para obtener más información, consulte [Eliminar una fila &#40;complemento MDS para Excel&#41;](delete-a-row-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="f3433-107">For more information, see [Delete a Row &#40;MDS Add-in for Excel&#41;](delete-a-row-mds-add-in-for-excel.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3433-108">La publicación no se puede usar para crear una entidad nueva.</span><span class="sxs-lookup"><span data-stu-id="f3433-108">Publishing cannot be used to create a new entity.</span></span> <span data-ttu-id="f3433-109">Para obtener más información sobre cómo crear entidades, consulte [Crear una entidad &#40;Complemento MDS para Excel&#41;](create-an-entity-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="f3433-109">For more information about creating entities, see [Create an Entity &#40;MDS Add-in for Excel&#41;](create-an-entity-mds-add-in-for-excel.md).</span></span>  
  
## <a name="when-multiple-users-publish-at-the-same-time"></a><span data-ttu-id="f3433-110">Cuando varios usuarios publican simultáneamente</span><span class="sxs-lookup"><span data-stu-id="f3433-110">When Multiple Users Publish at the Same Time</span></span>  
 <span data-ttu-id="f3433-111">Varios usuarios pueden publicar actualizaciones de los mismos datos.</span><span class="sxs-lookup"><span data-stu-id="f3433-111">Multiple users can publish updates to the same data.</span></span> <span data-ttu-id="f3433-112">A medida que cada usuario publica, la actualización se guarda en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f3433-112">As each user publishes, the update is saved to the database.</span></span> <span data-ttu-id="f3433-113">Esto significa que un usuario que no estaba trabajando con los datos actualizados más recientemente podrá cambiar el valor cuando los publique.</span><span class="sxs-lookup"><span data-stu-id="f3433-113">This means that a user who was not working with the most recently-updated data can still change the value when he or she publishes.</span></span>  
  
 <span data-ttu-id="f3433-114">Solo las actualizaciones que se realizan se publican en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f3433-114">Only the updates you make are published to the database.</span></span> <span data-ttu-id="f3433-115">Los datos obsoletos de la hoja de cálculo no se publican.</span><span class="sxs-lookup"><span data-stu-id="f3433-115">Any out-of-date data in the worksheet is not published.</span></span>  
  
## <a name="transactions-and-annotations"></a><span data-ttu-id="f3433-116">Transacciones y anotaciones</span><span class="sxs-lookup"><span data-stu-id="f3433-116">Transactions and Annotations</span></span>  
 <span data-ttu-id="f3433-117">Cada cambio publicado se guarda como una transacción.</span><span class="sxs-lookup"><span data-stu-id="f3433-117">Each published change is saved as a transaction.</span></span> <span data-ttu-id="f3433-118">Si lo desea, puede agregar anotaciones (comentarios) a una transacción para explicar por qué se realizó el cambio.</span><span class="sxs-lookup"><span data-stu-id="f3433-118">If you choose, you can add annotations (comments) to a transaction, to explain why you made the change.</span></span>  
  
-   <span data-ttu-id="f3433-119">No puede anotar las eliminaciones, aunque se guardan como transacciones que un administrador puede invertir.</span><span class="sxs-lookup"><span data-stu-id="f3433-119">You cannot annotate deletions, although deletions are saved as transactions that can be reversed by an administrator.</span></span>  
  
-   <span data-ttu-id="f3433-120">Si cambia el valor de **código** de un miembro, no se registrará como una transacción y todas las transacciones anteriores del miembro no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="f3433-120">If you change the **Code** value for a member, it is not recorded as a transaction, and all previous transactions for the member are unavailable.</span></span>  
  
-   <span data-ttu-id="f3433-121">Puede ver las transacciones realizadas por otros usuarios en un miembro.</span><span class="sxs-lookup"><span data-stu-id="f3433-121">You can view transactions made to a member by other users.</span></span> <span data-ttu-id="f3433-122">También puede ver todas las transacciones que ha realizado en un miembro, aunque ya no tenga permiso para atributos concretos.</span><span class="sxs-lookup"><span data-stu-id="f3433-122">You can also view all transactions you've made to a member, even if you no longer have permission to specific attributes.</span></span>  
  
 <span data-ttu-id="f3433-123">Puede ver todas las transacciones realizadas en un miembro.</span><span class="sxs-lookup"><span data-stu-id="f3433-123">You can view all transactions made to a member.</span></span> <span data-ttu-id="f3433-124">Para obtener más información, consulte [Ver todas las anotaciones o transacciones de un miembro &#40;complemento MDS para Excel&#41;](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="f3433-124">For more information, see [View All Annotations or Transactions for a Member &#40;MDS Add-in for Excel&#41;](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f3433-125">Si especifica una anotación de más de 500 caracteres, se trunca automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f3433-125">If you enter an annotation of more than 500 characters, the annotation is automatically truncated.</span></span>  
  
## <a name="business-rule-and-other-validation"></a><span data-ttu-id="f3433-126">Regla de negocios y otras validaciones</span><span class="sxs-lookup"><span data-stu-id="f3433-126">Business Rule and Other Validation</span></span>  
 <span data-ttu-id="f3433-127">Al publicar datos, se realiza la validación para asegurarse de que los datos son precisos antes de agregarlos al repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="f3433-127">When you publish data, validation is performed to ensure data is accurate before it's added to the MDS repository.</span></span> <span data-ttu-id="f3433-128">Si los datos no cumplen los criterios especificados, no se publicarán en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="f3433-128">If the data does not meet specified criteria, it will not be published to the repository.</span></span> <span data-ttu-id="f3433-129">Para obtener más información, consulte [Validar datos &#40;complemento MDS para Excel&#41;](validating-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="f3433-129">For more information, see [Validating Data &#40;MDS Add-in for Excel&#41;](validating-data-mds-add-in-for-excel.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f3433-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f3433-130">Related Tasks</span></span>  
  
|<span data-ttu-id="f3433-131">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="f3433-131">Task Description</span></span>|<span data-ttu-id="f3433-132">Tema</span><span class="sxs-lookup"><span data-stu-id="f3433-132">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="f3433-133">Publicar de nuevo los datos de la hoja de cálculo activa en el repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="f3433-133">Publish data from the active worksheet back to the MDS repository.</span></span>|[<span data-ttu-id="f3433-134">Publicar datos de Excel en MDS &#40;Complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="f3433-134">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)|  
|<span data-ttu-id="f3433-135">Eliminar una fila del repositorio MDS y de la hoja de cálculo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f3433-135">Delete a row from the MDS repository and from the worksheet at the same time.</span></span>|[<span data-ttu-id="f3433-136">Eliminar una fila &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="f3433-136">Delete a Row &#40;MDS Add-in for Excel&#41;</span></span>](delete-a-row-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="f3433-137">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="f3433-137">Related Content</span></span>  
  
-   [<span data-ttu-id="f3433-138">Actualizar datos &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="f3433-138">Refreshing Data &#40;MDS Add-in for Excel&#41;</span></span>](refreshing-data-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="f3433-139">Complemento Master Data Services para Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="f3433-139">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
