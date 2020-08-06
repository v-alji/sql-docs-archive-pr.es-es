---
title: Distribuidor | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replicationutilities.selectdistributor.f1
ms.assetid: 787f0e9c-09dd-438a-bc04-5b8f99c127b8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c601a540088b5cd9d7a2033510a5cf9b83c3170e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663376"
---
# <a name="distributor"></a><span data-ttu-id="d53a4-102">Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d53a4-102">Distributor</span></span>
  <span data-ttu-id="d53a4-103">La página **Distribuidor** aparece en el Asistente para configurar la distribución y en el Asistente para nueva publicación.</span><span class="sxs-lookup"><span data-stu-id="d53a4-103">The **Distributor** page appears in the Configure Distribution Wizard and in the New Publication Wizard.</span></span> <span data-ttu-id="d53a4-104">El distribuidor es un servidor que contiene la base de datos de distribución y almacena los metadatos y los datos del historial para todos los tipos de replicación.</span><span class="sxs-lookup"><span data-stu-id="d53a4-104">The Distributor is a server that contains the distribution database and stores metadata and history data for all types of replication.</span></span> <span data-ttu-id="d53a4-105">El distribuidor también almacena las transacciones para la replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="d53a4-105">The Distributor also stores transactions for transactional replication.</span></span> <span data-ttu-id="d53a4-106">El distribuidor puede ser el mismo servidor que el publicador (distribuidor local) o un servidor independiente del publicador (distribuidor remoto).</span><span class="sxs-lookup"><span data-stu-id="d53a4-106">The Distributor can be the same server as the Publisher (a local Distributor) or it can be a separate server from the Publisher (a remote Distributor).</span></span> <span data-ttu-id="d53a4-107">El rol del distribuidor varía según el tipo de replicación implementada.</span><span class="sxs-lookup"><span data-stu-id="d53a4-107">The role of the Distributor varies, depending on which type of replication you implement.</span></span> <span data-ttu-id="d53a4-108">Por lo general, es mayor el rol para la replicación transaccional que para la replicación de mezcla y de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="d53a4-108">In general, its role is much greater for transactional replication than it is for merge replication and snapshot replication.</span></span> <span data-ttu-id="d53a4-109">Las replicaciones de mezcla y de instantáneas usan generalmente un distribuidor local, pero la replicación transaccional en un sistema muy ocupado puede beneficiarse de usar un distribuidor remoto.</span><span class="sxs-lookup"><span data-stu-id="d53a4-109">Merge and snapshot replication typically use a local Distributor, but transactional replication on a very busy system can benefit from using a remote Distributor.</span></span>  
  
 <span data-ttu-id="d53a4-110">El distribuidor utiliza estos recursos adicionales en el servidor en el que se encuentra:</span><span class="sxs-lookup"><span data-stu-id="d53a4-110">The Distributor uses these additional resources on the server where it is located:</span></span>  
  
-   <span data-ttu-id="d53a4-111">Espacio de disco adicional si los archivos de instantáneas para la publicación se almacenan en éste (lo que ocurre habitualmente).</span><span class="sxs-lookup"><span data-stu-id="d53a4-111">Additional disk space if the snapshot files for the publication are stored on it (which they typically are).</span></span>  
  
-   <span data-ttu-id="d53a4-112">Espacio de disco adicional para almacenar la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="d53a4-112">Additional disk space to store the distribution database.</span></span>  
  
-   <span data-ttu-id="d53a4-113">Uso adicional del procesador por los agentes de replicación para las suscripciones de inserción que se ejecutan en el distribuidor</span><span class="sxs-lookup"><span data-stu-id="d53a4-113">Additional processor usage by replication agents for push subscriptions running on the Distributor.</span></span>  
  
 <span data-ttu-id="d53a4-114">El servidor seleccionado como distribuidor debe disponer del espacio en disco y la capacidad de proceso adecuados para la replicación y cualquier otra actividad asignada a ese servidor.</span><span class="sxs-lookup"><span data-stu-id="d53a4-114">The server you select as the Distributor should have adequate disk space and processor power to support replication and any other activities on that server.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d53a4-115">Opciones</span><span class="sxs-lookup"><span data-stu-id="d53a4-115">Options</span></span>  
 <span data-ttu-id="d53a4-116">**"\<ServerName>" actuará como su propio distribuidor; SQL Server creará una base de datos y un registro de distribución**.</span><span class="sxs-lookup"><span data-stu-id="d53a4-116">**'\<ServerName>' will act as its own Distributor; SQL Server will create a distribution database and log**</span></span>  
 <span data-ttu-id="d53a4-117">Seleccione esta opción para configurar el servidor al que está conectado como distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d53a4-117">Select this option to configure the server you are connected to as a Distributor.</span></span>  
  
 <span data-ttu-id="d53a4-118">**Utilizar el siguiente servidor como distribuidor  (Nota: el servidor que selecciona debe estar previamente configurado como distribuidor)**</span><span class="sxs-lookup"><span data-stu-id="d53a4-118">**Use the following server as the Distributor (Note: the server you select must already be configured as a Distributor)**</span></span>  
 <span data-ttu-id="d53a4-119">Seleccione esta opción y haga clic en el nombre de uno de los servidores que se muestran a continuación para configurar otro servidor como distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d53a4-119">Select this option and then click on the name of a server below to configure another server as the Distributor.</span></span>  
  
 <span data-ttu-id="d53a4-120">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="d53a4-120">**Add**</span></span>  
 <span data-ttu-id="d53a4-121">Si no se muestra el servidor que desea usar como distribuidor, haga clic en **Agregar** para identificar el servidor y agregarlo a la lista.</span><span class="sxs-lookup"><span data-stu-id="d53a4-121">If the server you want to use as a Distributor is not listed, click **Add** to identify the server and add it to the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d53a4-122">Para usar un servidor remoto como distribuidor, el servidor remoto debe estar configurado como distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d53a4-122">To use a remote server as the Distributor, the remote server must already be configured as a Distributor.</span></span> <span data-ttu-id="d53a4-123">Debe habilitar el servidor con el que se ejecuta el asistente como publicador en dicho distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d53a4-123">The server against which this wizard is running must be enabled as a Publisher on that Distributor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d53a4-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d53a4-124">See Also</span></span>  
 <span data-ttu-id="d53a4-125">[Configurar distribución](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="d53a4-125">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="d53a4-126">Configurar la publicación y la distribución</span><span class="sxs-lookup"><span data-stu-id="d53a4-126">Configure Publishing and Distribution</span></span>](configure-publishing-and-distribution.md)  
  
  
