---
title: Agente SQL Server servicio no puede usar la autenticación de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- authentication [SQL Server Agent]
- SQL Server Authentication [SQL Server Agent]
ms.assetid: c39f3ec3-fc2c-4c12-940f-60d8d3d17660
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 32188b1c47168aefbca914fa15f71850df716153
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674549"
---
# <a name="sql-server-agent-service-cannot-use-sql-server-authentication"></a><span data-ttu-id="ac84a-102">El servicio del Agente SQL Server no puede utilizar la autenticación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ac84a-102">SQL Server Agent Service cannot use SQL Server Authentication</span></span>
  <span data-ttu-id="ac84a-103">El Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] solo es compatible con la autenticación de Windows cuando el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se conecta a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac84a-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent only supports Windows Authentication when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service connects to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="ac84a-104">Componente</span><span class="sxs-lookup"><span data-stu-id="ac84a-104">Component</span></span>  
 <span data-ttu-id="ac84a-105">e[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac84a-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="ac84a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac84a-106">Description</span></span>  
 <span data-ttu-id="ac84a-107">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] solo puede sesión en la base de datos utilizando la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="ac84a-107">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can only log on to the database using Windows Authentication.</span></span> <span data-ttu-id="ac84a-108">Esto significa que la cuenta del servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe corresponder a un usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac84a-108">This means that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account must be a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user.</span></span>  
  
 <span data-ttu-id="ac84a-109">Para obtener más información, consulte los temas "Seguridad para la administración automática" e "Implementar la seguridad del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac84a-109">For more information, see the topics "Security for Automatic Administration" and "Implementing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Security" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac84a-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac84a-110">See Also</span></span>  
 [<span data-ttu-id="ac84a-111">Problemas de actualización del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="ac84a-111">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
