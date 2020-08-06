---
title: Base de datos de distribución | Microsoft Docs
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configuredistributionwizard.distributiondatabase.f1
ms.assetid: 5b42a083-7a11-41d8-9e3f-320c7c907237
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d98a80be52ae77cbdaf1581a5b3397f9d11af4fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663388"
---
# <a name="distribution-database"></a><span data-ttu-id="da613-102">Base de datos de distribución</span><span class="sxs-lookup"><span data-stu-id="da613-102">Distribution Database</span></span>
  <span data-ttu-id="da613-103">En la base de datos de distribución se almacenan metadatos y datos del historial de todos los tipos de replicación y transacciones de replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="da613-103">The distribution database stores metadata and history data for all types of replication, and transactions for transactional replication.</span></span>  
  
 <span data-ttu-id="da613-104">En muchas ocasiones, una sola base de datos de distribución resulta suficiente.</span><span class="sxs-lookup"><span data-stu-id="da613-104">In many cases, a single distribution database is sufficient.</span></span> <span data-ttu-id="da613-105">No obstante, si varios publicadores utilizan un único distribuidor, considere la posibilidad de crear una base de datos de distribución para cada publicador.</span><span class="sxs-lookup"><span data-stu-id="da613-105">However, if multiple Publishers use a single Distributor, consider creating a distribution database for each Publisher.</span></span> <span data-ttu-id="da613-106">De esta forma, se garantiza que los datos que pasan por cada base de datos de distribución son distintos.</span><span class="sxs-lookup"><span data-stu-id="da613-106">Doing so ensures that the data flowing through each distribution database is distinct.</span></span> <span data-ttu-id="da613-107">Para especificar una base de datos de distribución para el distribuidor, puede utilizar el Asistente para configurar la distribución.</span><span class="sxs-lookup"><span data-stu-id="da613-107">You can specify one distribution database for the Distributor using the Configure Distribution Wizard.</span></span> <span data-ttu-id="da613-108">Si es necesario, especifique bases de datos de distribución adicionales en el cuadro de diálogo **Propiedades del distribuidor** .</span><span class="sxs-lookup"><span data-stu-id="da613-108">If necessary, specify additional distribution databases in the **Distributor Properties** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="da613-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="da613-109">Options</span></span>  
 <span data-ttu-id="da613-110">**Nombre de base de datos de distribución**</span><span class="sxs-lookup"><span data-stu-id="da613-110">**Distribution database name**</span></span>  
 <span data-ttu-id="da613-111">Escriba el nombre de la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="da613-111">Enter a name for the distribution database.</span></span> <span data-ttu-id="da613-112">El nombre predeterminado de la base de datos de distribución es "distribution".</span><span class="sxs-lookup"><span data-stu-id="da613-112">The default name for the distribution database is 'distribution'.</span></span> <span data-ttu-id="da613-113">Si especifica un nombre, este puede tener como máximo 128 caracteres, debe ser único dentro de una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y debe respetar las reglas de los identificadores.</span><span class="sxs-lookup"><span data-stu-id="da613-113">If you specify a name, the name can be a maximum of 128 characters, must be unique within an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and must conform to the rules for identifiers.</span></span> <span data-ttu-id="da613-114">Para obtener más información, vea [Database Identifiers](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="da613-114">For more information, see [Database Identifiers](../databases/database-identifiers.md).</span></span>  
  
 <span data-ttu-id="da613-115">**Carpeta para el archivo de la base de datos de distribución** y **Carpeta para el archivo de registro de la base de datos de distribución**</span><span class="sxs-lookup"><span data-stu-id="da613-115">**Folder for the distribution database file** and **Folder for the distribution database log file**</span></span>  
 <span data-ttu-id="da613-116">Escriba la ruta de acceso de la base de datos de distribución y los archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="da613-116">Enter the path for the distribution database and log files.</span></span> <span data-ttu-id="da613-117">Las rutas de acceso deben hacer referencia a discos locales del distribuidor y empezar con una letra de unidad y dos puntos (por ejemplo, C:).</span><span class="sxs-lookup"><span data-stu-id="da613-117">Paths must refer to disks that are local to the Distributor and begin with a local drive letter and colon (for example, C:).</span></span> <span data-ttu-id="da613-118">No puede utilizar rutas de acceso de redes ni letras de unidades asignadas.</span><span class="sxs-lookup"><span data-stu-id="da613-118">Mapped drive letters and network paths are not valid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da613-119">Puede reducir el tiempo que se tarda en escribir las transacciones y mejorar el rendimiento de la replicación si coloca el registro de la base de datos de distribución en una unidad de disco separada de la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="da613-119">You can decrease the time it takes to write transactions and improve the performance of replication by placing the distribution database log on a separate disk drive from the distribution database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da613-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="da613-120">See Also</span></span>  
 <span data-ttu-id="da613-121">[Configurar distribución](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="da613-121">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="da613-122">[Configurar la publicación y la distribución](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="da613-122">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 [<span data-ttu-id="da613-123">Ver y modificar las propiedades del distribuidor y del publicador</span><span class="sxs-lookup"><span data-stu-id="da613-123">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)  
  
  
