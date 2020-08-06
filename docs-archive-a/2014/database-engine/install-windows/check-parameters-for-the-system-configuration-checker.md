---
title: Comprobar los parámetros del Comprobador de configuración del sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- installing SQL Server, system configuration checks
- failed system configuration checks [SQL Server]
- verifying configuration before installation
- SCC [SQL Server]
- system configuration checker
- scanning computer before installation [SQL Server]
- checking configuration before installation
- status information [SQL Server], system configuration checker
- parameters [SQL Server], system configuration checker
- configuration checkers [SQL Server]
- Setup [SQL Server], system configuration checker
ms.assetid: 8e712c15-6bfa-4d71-b303-9526101e5594
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0bf159d3c6184974d108075cd65e32b449d441bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747173"
---
# <a name="check-parameters-for-the-system-configuration-checker"></a><span data-ttu-id="da23b-102">Comprobar los parámetros del Comprobador de configuración del sistema</span><span class="sxs-lookup"><span data-stu-id="da23b-102">Check Parameters for the System Configuration Checker</span></span>
  <span data-ttu-id="da23b-103">Durante la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , el Comprobador de configuración del sistema (SCC) examina el equipo en el que se instalará [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da23b-103">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the System Configuration Checker (SCC) scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed.</span></span> <span data-ttu-id="da23b-104">El SCC comprueba las condicione que impiden una instalación correcta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da23b-104">The SCC checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="da23b-105">Antes de que el programa de instalación inicie el Asistente para la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , el SCC recupera el estado de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="da23b-105">Before Setup starts the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard, the SCC retrieves the status of each item.</span></span> <span data-ttu-id="da23b-106">A continuación, compara el resultado con las condiciones necesarias y proporciona instrucciones para evitar problemas de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="da23b-106">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="da23b-107">El comprobador de la configuración del sistema genera un informe que contiene una descripción breve de cada regla ejecutada y el estado de ejecución.</span><span class="sxs-lookup"><span data-stu-id="da23b-107">The system configuration checker generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="da23b-108">El informe de comprobación de la configuración del sistema se encuentra en% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="da23b-108">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da23b-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="da23b-109">See Also</span></span>  
 <span data-ttu-id="da23b-110">[Requisitos de hardware y software para la instalación de SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="da23b-110">[Hardware and Software Requirements for Installing SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md) </span></span>  
 <span data-ttu-id="da23b-111">[Consideraciones de seguridad para una instalación de SQL Server](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="da23b-111">[Security Considerations for a SQL Server Installation](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="da23b-112">Actualizaciones de ediciones y versiones admitidas</span><span class="sxs-lookup"><span data-stu-id="da23b-112">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
  
