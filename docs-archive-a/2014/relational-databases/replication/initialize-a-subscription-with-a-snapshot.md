---
title: Inicializar una suscripción con una instantánea | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- snapshots [SQL Server replication], initializing subscriptions
- initializing subscriptions [SQL Server replication], snapshots
ms.assetid: 77a9ade2-cdc0-4ae9-a02d-6e29d7c2ada0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f8b776e71e9d1197bc174169aee8ccf692884308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663348"
---
# <a name="initialize-a-subscription-with-a-snapshot"></a><span data-ttu-id="7e4b5-102">Inicializar una suscripción con una instantánea</span><span class="sxs-lookup"><span data-stu-id="7e4b5-102">Initialize a Subscription with a Snapshot</span></span>
  <span data-ttu-id="7e4b5-103">Una vez que se ha creado una publicación, normalmente se crea una instantánea inicial, que se copia en la carpeta de instantáneas (es así de manera predeterminada para las publicaciones de combinación creadas con el Asistente para nueva publicación.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-103">After a publication has been created, an initial snapshot is typically created and copied to the snapshot folder (this occurs by default for merge publications created with the New Publication Wizard).</span></span> <span data-ttu-id="7e4b5-104">A continuación, el Agente de distribución (para las publicaciones transaccionales y de instantáneas) o el Agente de mezcla (para las publicaciones de combinación) la aplican al suscriptor durante la sincronización inicial de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-104">It is then applied to the Subscriber by the Distribution Agent (for transactional and snapshot publications) or the Merge Agent (for merge publications) during the initial synchronization of the subscription.</span></span> <span data-ttu-id="7e4b5-105">El proceso de la instantánea depende del tipo de publicación:</span><span class="sxs-lookup"><span data-stu-id="7e4b5-105">The snapshot process depends on the type of publication:</span></span>  
  
-   <span data-ttu-id="7e4b5-106">Si la instantánea es para una publicación de instantáneas, una publicación transaccional o una publicación de combinación que no utiliza filtros con parámetros, contiene el esquema y los datos en archivos de programa de copia masiva (bcp), así como las restricciones, las propiedades extendidas, los índices, los desencadenadores y las tablas del sistema que se necesitan para la replicación.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-106">If the snapshot is for a snapshot publication, a transactional publication, or a merge publication that doesn't use parameterized filters, the snapshot contains the schema and data in bulk copy program (bcp) files, as well as constraints, extended properties, indexes, triggers, and the system tables necessary for replication.</span></span> <span data-ttu-id="7e4b5-107">Para más información acerca de la creación y aplicación de la instantánea, vea [Crear y aplicar una instantánea](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="7e4b5-107">For more information about creating and applying the snapshot, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
-   <span data-ttu-id="7e4b5-108">Si la instantánea es para una publicación de combinación que utiliza filtros con parámetros, se crea mediante un proceso de dos partes.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-108">If the snapshot is for a merge publication that uses parameterized filters, the snapshot is created using a two-part process.</span></span> <span data-ttu-id="7e4b5-109">En primer lugar se crea una instantánea del esquema que contiene los scripts y el esquema de replicación de los objetos publicados, pero no los datos.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-109">First a schema snapshot is created that contains the replication scripts and the schema of the published objects, but not the data.</span></span> <span data-ttu-id="7e4b5-110">A continuación, cada suscripción se inicializa con una instantánea que incluye los scripts y el esquema copiados de la instantánea de esquema y los datos que pertenecen a la partición de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-110">Each subscription is then initialized with a snapshot that includes the scripts and schema copied from the schema snapshot and the data that belongs to the subscription's partition.</span></span> <span data-ttu-id="7e4b5-111">Para más información, consulte [Instantáneas para publicaciones de combinación con filtros con parámetros](snapshots-for-merge-publications-with-parameterized-filters.md).</span><span class="sxs-lookup"><span data-stu-id="7e4b5-111">For more information, see [Snapshots for Merge Publications with Parameterized Filters](snapshots-for-merge-publications-with-parameterized-filters.md).</span></span>  
  
 <span data-ttu-id="7e4b5-112">La instantánea se compone de varios archivos, según el tipo de replicación y los artículos de la publicación.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-112">The snapshot consists of different files depending on the type of replication and the articles in your publication.</span></span> <span data-ttu-id="7e4b5-113">Estos archivos se copian en la carpeta de instantáneas predeterminada especificada al configurar el distribuidor o en la carpeta alternativa especificada al crear la publicación.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-113">These files are copied to the default snapshot folder specified when the Distributor was configured or the alternate snapshot folder specified when the publication was created.</span></span>  
  
|<span data-ttu-id="7e4b5-114">Tipo de replicación</span><span class="sxs-lookup"><span data-stu-id="7e4b5-114">Type of Replication</span></span>|<span data-ttu-id="7e4b5-115">Archivos comunes de instantánea</span><span class="sxs-lookup"><span data-stu-id="7e4b5-115">Common Snapshot Files</span></span>|  
|-------------------------|---------------------------|  
|<span data-ttu-id="7e4b5-116">Replicación de instantáneas o replicación transaccional</span><span class="sxs-lookup"><span data-stu-id="7e4b5-116">Snapshot Replication or Transactional Replication</span></span>|<span data-ttu-id="7e4b5-117">Esquemas (.sch), datos (.bcp), índices y restricciones (.dri), restricciones (.idx), desencadenadores (.trg) solo para actualizar suscriptores, archivos de instantáneas comprimidos (.cab).</span><span class="sxs-lookup"><span data-stu-id="7e4b5-117">schema (.sch); data (.bcp); constraints and indexes (.dri); constraints (.idx); triggers (.trg):for updating Subscribers only; compressed snapshot files (.cab).</span></span>|  
|<span data-ttu-id="7e4b5-118">Replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="7e4b5-118">Merge Replication</span></span>|<span data-ttu-id="7e4b5-119">Esquemas (.sch), datos (.bcp), índices y restricciones (.dri), desencadenadores (.trg), datos de tabla del sistema (.sys), tablas de conflictos (.cft), archivos de instantáneas comprimidos (.cab).</span><span class="sxs-lookup"><span data-stu-id="7e4b5-119">schema (.sch); data (.bcp); constraints and indexes (.dri); triggers (.trg); system table data (.sys); conflict tables (.cft); compressed snapshot files (.cab).</span></span>|  
  
 <span data-ttu-id="7e4b5-120">Si la transferencia de la instantánea se interrumpe en algún momento, continuará inmediatamente y no se volverá a enviar ningún archivo que ya hubiera sido transferido en su totalidad.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-120">If the snapshot transfer is interrupted at any point, it will automatically resume and will not resend any files that have already been completely transferred.</span></span> <span data-ttu-id="7e4b5-121">La unidad de entrega del Agente de instantáneas es el archivo bcp de cada artículo de la publicación, de modo que los archivos entregados parcialmente deben volverse a entregar completamente.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-121">The unit of delivery for the Snapshot Agent is the bcp file for each publication article, so files that are partially delivered must be completely redelivered.</span></span> <span data-ttu-id="7e4b5-122">No obstante, continuar con la instantánea puede reducir de forma significativa la cantidad de datos transmitidos y garantizar una entrega a tiempo de la instantánea aunque la conexión no sea de confianza.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-122">However, resuming the snapshot can significantly reduce the amount of data transmitted and ensure timely snapshot delivery even if the connection is unreliable.</span></span>  
  
## <a name="snapshot-options"></a><span data-ttu-id="7e4b5-123">Opciones de instantánea</span><span class="sxs-lookup"><span data-stu-id="7e4b5-123">Snapshot Options</span></span>  
 <span data-ttu-id="7e4b5-124">Hay una serie de opciones disponibles al inicializar una suscripción con una instantánea.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-124">There are a number of options available when initializing a subscription with a snapshot.</span></span> <span data-ttu-id="7e4b5-125">Puede:</span><span class="sxs-lookup"><span data-stu-id="7e4b5-125">You can:</span></span>  
  
-   <span data-ttu-id="7e4b5-126">Especificar una ubicación alternativa para la carpeta de instantáneas en lugar de, o además de, la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-126">Specify an alternate snapshot folder location instead of, or in addition, to the default snapshot folder location.</span></span> <span data-ttu-id="7e4b5-127">Para más información, consulte [Alternate Snapshot Folder Locations](alternate-snapshot-folder-locations.md).</span><span class="sxs-lookup"><span data-stu-id="7e4b5-127">For more information, see [Alternate Snapshot Folder Locations](alternate-snapshot-folder-locations.md).</span></span>  
  
-   <span data-ttu-id="7e4b5-128">Comprimir instantáneas para su almacenamiento en medios extraíbles o para su transferencia a través de una red lenta.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-128">Compress snapshots for storage on removable media or for transfer over a slow network.</span></span> <span data-ttu-id="7e4b5-129">Para más información, consulte [Compressed Snapshots](compressed-snapshots.md).</span><span class="sxs-lookup"><span data-stu-id="7e4b5-129">For more information, see [Compressed Snapshots](compressed-snapshots.md).</span></span>  
  
-   <span data-ttu-id="7e4b5-130">Ejecutar scripts Transact-SQL antes o después de aplicar la instantánea.</span><span class="sxs-lookup"><span data-stu-id="7e4b5-130">Execute Transact-SQL scripts before or after the snapshot is applied.</span></span> <span data-ttu-id="7e4b5-131">Para obtener más información, consulte [Ejecutar scripts antes y después de aplicar la instantánea](snapshot-options.md#execute-scripts-before-and-after-snapshot-is-applied).</span><span class="sxs-lookup"><span data-stu-id="7e4b5-131">For more information, see [Execute Scripts Before and After the Snapshot Is Applied](snapshot-options.md#execute-scripts-before-and-after-snapshot-is-applied).</span></span>  
  
-   <span data-ttu-id="7e4b5-132">Transferir la instantánea mediante el Protocolo de transferencia de archivos (FTP).</span><span class="sxs-lookup"><span data-stu-id="7e4b5-132">Transfer snapshot files using File Transfer Protocol (FTP).</span></span> <span data-ttu-id="7e4b5-133">Para obtener más información, vea [Transferir instantáneas mediante FTP](transfer-snapshots-through-ftp.md).</span><span class="sxs-lookup"><span data-stu-id="7e4b5-133">For more information, see [Transfer Snapshots Through FTP](transfer-snapshots-through-ftp.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e4b5-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e4b5-134">See Also</span></span>  
 <span data-ttu-id="7e4b5-135">[Initialize a Subscription](initialize-a-subscription.md)  (Inicializar una suscripción)</span><span class="sxs-lookup"><span data-stu-id="7e4b5-135">[Initialize a Subscription](initialize-a-subscription.md) </span></span>  
 [<span data-ttu-id="7e4b5-136">Proteger la carpeta de instantáneas</span><span class="sxs-lookup"><span data-stu-id="7e4b5-136">Secure the Snapshot Folder</span></span>](security/secure-the-snapshot-folder.md)  
  
  