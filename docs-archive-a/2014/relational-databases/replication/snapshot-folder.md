---
title: Carpeta de instantáneas | Microsoft Docs
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replicationutilities.specifysnapshotfolder.f1
ms.assetid: 3eb1b73f-ddb3-4d09-be6e-811c414698e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 48b490c65662edf65018e98dd1bc3339f6aae6b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677531"
---
# <a name="snapshot-folder"></a><span data-ttu-id="94a0c-102">Carpeta de instantáneas</span><span class="sxs-lookup"><span data-stu-id="94a0c-102">Snapshot Folder</span></span>
  <span data-ttu-id="94a0c-103">La página **Carpeta de instantáneas** aparece en el Asistente para configurar la distribución y en el Asistente para nueva publicación.</span><span class="sxs-lookup"><span data-stu-id="94a0c-103">The **Snapshot Folder** page appears in the Configure Distribution Wizard and in the New Publication Wizard.</span></span> <span data-ttu-id="94a0c-104">La ubicación que se especifique para la carpeta de instantáneas se utilizará como la predeterminada para todos los publicadores habilitados en este asistente (la carpeta de instantáneas predeterminada no se aplica a los publicadores que se habilitan posteriormente mediante el cuadro de diálogo **Propiedades del distribuidor** ).</span><span class="sxs-lookup"><span data-stu-id="94a0c-104">The location you specify for the snapshot folder will be used as the default for all Publishers enabled in this wizard (the default snapshot folder does not apply to Publishers that are later enabled using the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="94a0c-105">Puede sobrescribir este valor predeterminado en cualquier publicador de la página **Publicadores** del Asistente para configurar la distribución o el cuadro de diálogo **Propiedades del distribuidor** .</span><span class="sxs-lookup"><span data-stu-id="94a0c-105">You can override this default for any Publisher on the **Publishers** page of the Configure Distribution Wizard or the **Distributor Properties** dialog box.</span></span>  
  
 <span data-ttu-id="94a0c-106">La carpeta de instantáneas es simplemente un directorio designado como recurso compartido; los agentes que leen y escriben en esta carpeta deben tener permisos de acceso suficientes a ella.</span><span class="sxs-lookup"><span data-stu-id="94a0c-106">The snapshot folder is simply a directory that you have designated as a share; agents that read from and write to this folder must have sufficient permissions to access it.</span></span> <span data-ttu-id="94a0c-107">Para obtener más información sobre cómo proteger la carpeta adecuadamente, vea [Proteger la carpeta de instantáneas](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="94a0c-107">For more information about securing the folder appropriately, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span> <span data-ttu-id="94a0c-108">Antes de implementar la replicación, compruebe que los agentes de replicación podrán conectarse a la carpeta de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="94a0c-108">Prior to implementing replication, test that the replication agents will be able to connect to the snapshot folder.</span></span> <span data-ttu-id="94a0c-109">Inicie la sesión con la cuenta que utilizará cada agente y, a continuación, intente tener acceso a la carpeta de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="94a0c-109">Log on under the account that will be used by each agent and then attempt to access the snapshot folder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="94a0c-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="94a0c-110">Options</span></span>  
 <span data-ttu-id="94a0c-111">**Carpeta de instantáneas**</span><span class="sxs-lookup"><span data-stu-id="94a0c-111">**Snapshot folder**</span></span>  
 <span data-ttu-id="94a0c-112">Escriba la ruta de acceso de la carpeta donde desea almacenar los archivos de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="94a0c-112">Enter the path for the folder where you want snapshot files stored.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="94a0c-113">recomienda utilizar un recurso de red compartido como ubicación para la carpeta de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="94a0c-113">recommends that you use a network share as a snapshot folder location.</span></span> <span data-ttu-id="94a0c-114">Los agentes en otros equipos no tienen acceso a las rutas de acceso locales (las que empiezan con una letra de unidad como C:\\).</span><span class="sxs-lookup"><span data-stu-id="94a0c-114">Local paths (those starting with a drive letter, such as C:\\) are not accessible to agents on other computers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a0c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94a0c-115">See Also</span></span>  
 <span data-ttu-id="94a0c-116">[Ubicaciones de carpeta de instantáneas alternativas](alternate-snapshot-folder-locations.md) </span><span class="sxs-lookup"><span data-stu-id="94a0c-116">[Alternate Snapshot Folder Locations](alternate-snapshot-folder-locations.md) </span></span>  
 <span data-ttu-id="94a0c-117">[Configurar distribución](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="94a0c-117">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="94a0c-118">[Configurar la publicación y la distribución](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="94a0c-118">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="94a0c-119">[Ver y modificar las propiedades del distribuidor y del publicador](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="94a0c-119">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="94a0c-120">Inicializar una suscripción con una instantánea</span><span class="sxs-lookup"><span data-stu-id="94a0c-120">Initialize a Subscription with a Snapshot</span></span>](initialize-a-subscription-with-a-snapshot.md)  
  
  
