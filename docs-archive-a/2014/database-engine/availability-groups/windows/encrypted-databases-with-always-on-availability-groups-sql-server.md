---
title: Bases de datos cifradas con Grupos de disponibilidad AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, AlwaysOn Availability Groups
- TDE, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 09eb6ebc-3051-4fff-86a5-93524507b1fc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 91e717a896634a7df5a96253c51207831f142cff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663713"
---
# <a name="encrypted-databases-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="13b1e-102">Bases de datos cifradas con grupos de disponibilidad AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="13b1e-102">Encrypted Databases with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="13b1e-103">Este tema contiene información sobre el uso de bases de datos actualmente cifradas o recientemente descifradas con [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13b1e-103">This topic contains information about the using currently encrypted or recently decrypted databases with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="13b1e-104">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="13b1e-104">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="13b1e-105">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="13b1e-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="13b1e-106">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="13b1e-106">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="13b1e-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="13b1e-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="13b1e-108">Si una base de datos está cifrada o incluso contiene una clave de cifrado de base de datos (DEK), no puede usar el [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] ni el [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] para agregar la base de datos a un grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="13b1e-108">If a database is encrypted or even contains a Database Encryption Key (DEK), you cannot use the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] or [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] to add the database to an availability group.</span></span> <span data-ttu-id="13b1e-109">Aunque se haya descifrado una base de datos cifrada, sus copias de seguridad de registros pueden contener datos cifrados.</span><span class="sxs-lookup"><span data-stu-id="13b1e-109">Even if an encrypted database has been decrypted, its log backups might contain encrypted data.</span></span> <span data-ttu-id="13b1e-110">En este caso, la sincronización de datos completa inicial podría producir errores en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="13b1e-110">In this case, full initial data synchronization could fail on the database.</span></span> <span data-ttu-id="13b1e-111">Esto se debe a que la operación de restaurar registro puede requerir el certificado utilizado por las claves de cifrado de base de datos (DEK) y ese certificado podría no estar disponible.</span><span class="sxs-lookup"><span data-stu-id="13b1e-111">This is because the restore log operation might require the certificate that was used by the database encryption keys (DEKs), and that certificate might be unavailable.</span></span>  
  
     <span data-ttu-id="13b1e-112">Para que una base de datos descifrada se pueda agregar a un grupo de disponibilidad mediante el asistente:</span><span class="sxs-lookup"><span data-stu-id="13b1e-112">To make a decrypted database eligible to add to an availability group using the wizard:</span></span>  
  
    1.  <span data-ttu-id="13b1e-113">Cree una copia de seguridad de registros de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="13b1e-113">Create a log backup of the primary database.</span></span>  
  
    2.  <span data-ttu-id="13b1e-114">Cree una copia de seguridad completa de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="13b1e-114">Create a full database backup of the primary database.</span></span>  
  
    3.  <span data-ttu-id="13b1e-115">Restaure la copia de seguridad de base de datos en la instancia del servidor que hospeda la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="13b1e-115">Restore the database backup on the server instance that hosts the secondary replica.</span></span>  
  
    4.  <span data-ttu-id="13b1e-116">Cree una nueva copia de seguridad de registros a partir de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="13b1e-116">Create a new log backup from primary database.</span></span>  
  
    5.  <span data-ttu-id="13b1e-117">Restaure esta copia de seguridad de registros en la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="13b1e-117">Restore this log backup on the secondary database.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="13b1e-118">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="13b1e-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="13b1e-119">Preparar manualmente una base de datos secundaria para un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="13b1e-119">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="13b1e-120">Usar el Asistente para grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="13b1e-120">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="13b1e-121">Usar el Asistente para agregar una base de datos al grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="13b1e-121">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="13b1e-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13b1e-122">See Also</span></span>  
 <span data-ttu-id="13b1e-123">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="13b1e-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="13b1e-124">Cifrado de datos transparente &#40;TDE&#41;</span><span class="sxs-lookup"><span data-stu-id="13b1e-124">Transparent Data Encryption &#40;TDE&#41;</span></span>](../../../relational-databases/security/encryption/transparent-data-encryption.md)  
  
  
