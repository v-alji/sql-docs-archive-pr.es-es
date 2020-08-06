---
title: Requisitos de la cuenta de servicio para actualizar a SQL Server 2008 en un controlador de dominio | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- domain controllers
- service accounts
- network service accounts
- local service accounts
ms.assetid: 574245b6-11e2-4849-b0ca-836d673ecd0d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0680e09548e38760f6ac317fec63152486a4e5fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672447"
---
# <a name="service-account-requirements-for-upgrading-to-sql-server-2008-on-a-domain-controller"></a><span data-ttu-id="de751-102">Requisitos de cuenta de servicio para actualizar a SQL Server 2008 en un controlador de dominio</span><span class="sxs-lookup"><span data-stu-id="de751-102">Service account requirements for upgrading to SQL Server 2008 on a domain controller</span></span>
  <span data-ttu-id="de751-103">El asesor de actualizaciones ha detectado una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ejecuta bajo una cuenta de servicio de red o de servicio local en un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="de751-103">Upgrade Advisor detected an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running under a Network Service or Local Service account on a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] domain controller.</span></span> <span data-ttu-id="de751-104">Cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se instala en un controlador de dominio [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], los servicios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se pueden ejecutar con los privilegios de una cuenta de servicio local o de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="de751-104">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] domain controller, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services cannot run under Local Service account or Network Service account privileges.</span></span>  
  
## <a name="component"></a><span data-ttu-id="de751-105">Componente</span><span class="sxs-lookup"><span data-stu-id="de751-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="de751-106">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="de751-106">Corrective Action</span></span>  
 <span data-ttu-id="de751-107">Asegúrese de que todas las cuentas de servicio de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] están asignadas a cuentas de dominio o a cuentas de sistema locales.</span><span class="sxs-lookup"><span data-stu-id="de751-107">Make sure that all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service accounts are assigned to either Domain accounts or Local System accounts.</span></span> <span data-ttu-id="de751-108">Si no se realiza esta modificación antes de actualizar, la instalación se bloqueará.</span><span class="sxs-lookup"><span data-stu-id="de751-108">Failure to make this change before upgrading will block Setup.</span></span> <span data-ttu-id="de751-109">Se exceptúan el Objeto de escritura de SQL de las cuentas de servicio y el Servicio del asistente de Active Directory de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ya que están codificados de forma rígida en la cuenta del servicio de red y no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="de751-109">The service accounts SQL Writer, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Active Directory Helper services are exceptions because they are hard-coded to the Network Service account and cannot be changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de751-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de751-110">See Also</span></span>  
 <span data-ttu-id="de751-111">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="de751-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="de751-112">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="de751-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
