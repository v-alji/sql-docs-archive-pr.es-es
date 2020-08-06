---
title: Comprobar el subsistema de salida de entrada de disco para problemas de reintento de lectura | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: cedf4097-5b73-4964-9935-74a101847019
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19809b1554e435600eb4eeae424bed17dc27bdbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744071"
---
# <a name="check-disk-input-output-subsystem-for-read-retry-problems"></a><span data-ttu-id="64493-102">Comprobación de la existencia de problemas de reintento de lectura en el subsistema de entrada y salida del disco</span><span class="sxs-lookup"><span data-stu-id="64493-102">Check Disk Input Output Subsystem for Read Retry Problems</span></span>
  <span data-ttu-id="64493-103">Esta regla comprueba si existe el mensaje de error 825 de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="64493-103">This rule checks the event log for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message 825.</span></span> <span data-ttu-id="64493-104">Este mensaje indica que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no pudo leer los datos del disco al primer intento.</span><span class="sxs-lookup"><span data-stu-id="64493-104">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was unable to read data from the disk on the first try.</span></span> <span data-ttu-id="64493-105">Este mensaje indica un problema importante con el subsistema de E/S de disco.</span><span class="sxs-lookup"><span data-stu-id="64493-105">This message indicates a major problem with the disk I/O subsystem.</span></span> <span data-ttu-id="64493-106">Este mensaje no indica actualmente un problema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64493-106">This message does not currently indicate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] problem.</span></span> <span data-ttu-id="64493-107">Sin embargo, el problema de disco podría producir la pérdida de datos o daños en la base de datos si no se resuelve.</span><span class="sxs-lookup"><span data-stu-id="64493-107">However, the disk problem could cause data loss or database corruption if it is not resolved.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="64493-108">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="64493-108">Best Practices Recommendations</span></span>  
 <span data-ttu-id="64493-109">Las siguientes acciones podrían ayudarle a detectar y resolver el problema de hardware subyacente:</span><span class="sxs-lookup"><span data-stu-id="64493-109">The following actions might help you discover and resolve the underlying hardware problem:</span></span>  
  
-   <span data-ttu-id="64493-110">Revise el registro de errores y el texto variable de este mensaje para obtener pistas que expliquen el problema.</span><span class="sxs-lookup"><span data-stu-id="64493-110">Review the error log and the variable text in this message for clues that explain the problem.</span></span>  
  
-   <span data-ttu-id="64493-111">Compruebe el sistema de disco.</span><span class="sxs-lookup"><span data-stu-id="64493-111">Check the disk system.</span></span> <span data-ttu-id="64493-112">El problema podría estar relacionado con discos, controladores de discos, tarjetas de matriz o unidades de disco.</span><span class="sxs-lookup"><span data-stu-id="64493-112">The problem could be related to the disks, the disk controllers, array cards, or disk drivers.</span></span>  
  
-   <span data-ttu-id="64493-113">Póngase en contacto con el fabricante del disco para obtener las utilidades más recientes a fin de comprobar el estado del sistema de disco.</span><span class="sxs-lookup"><span data-stu-id="64493-113">Contact the disk manufacturer for the latest utilities for checking the status of the disk system.</span></span>  
  
-   <span data-ttu-id="64493-114">Póngase en contacto con el fabricante del disco para obtener las últimas actualizaciones del controlador.</span><span class="sxs-lookup"><span data-stu-id="64493-114">Contact the disk manufacturer for the latest driver updates.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="64493-115">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="64493-115">For More Information</span></span>  
 [<span data-ttu-id="64493-116">MSSQLSERVER_825</span><span class="sxs-lookup"><span data-stu-id="64493-116">MSSQLSERVER_825</span></span>](../errors-events/mssqlserver-825-database-engine-error.md)  
  
 <span data-ttu-id="64493-117">[Elementos fundamentales de E/S de SQL Server, capítulo 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="64493-117">[SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span></span>  
  
  
