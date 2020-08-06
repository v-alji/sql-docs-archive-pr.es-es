---
title: Propiedades de Agente SQL Server (página Conexión) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.connection.f1
ms.assetid: d6a677ff-60ad-47ba-a0cb-df4193b165e0
author: stevestein
ms.author: sstein
ms.openlocfilehash: ec9ae575f1ced510d95256d6827435e5b6ad89d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676303"
---
# <a name="sql-server-agent-properties-connection-page"></a><span data-ttu-id="896a6-102">Propiedades de Agente SQL Server (página Conexión)</span><span class="sxs-lookup"><span data-stu-id="896a6-102">SQL Server Agent Properties (Connection Page)</span></span>
  <span data-ttu-id="896a6-103">Utilice esta página para ver y modificar la configuración de la conexión del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servicio agente a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="896a6-103">Use this page to view and modify the settings for the connection from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="896a6-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="896a6-104">Options</span></span>  
 <span data-ttu-id="896a6-105">**Servidor de host local del alias**</span><span class="sxs-lookup"><span data-stu-id="896a6-105">**Alias local host server**</span></span>  
 <span data-ttu-id="896a6-106">Especifica el alias que debe utilizarse para conectarse a la instancia local de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="896a6-106">Specifies the alias to use to connect to the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="896a6-107">Si no puede utilizar las opciones de conexión predeterminadas del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , defina un alias para la instancia y especifíquelo aquí.</span><span class="sxs-lookup"><span data-stu-id="896a6-107">If you cannot use the default connection options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, define an alias for the instance and specify the alias here.</span></span>  
  
 <span data-ttu-id="896a6-108">**Utilizar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="896a6-108">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="896a6-109">Establece la autenticación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows como método de autenticación que se utiliza para conectarse a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="896a6-109">Sets [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication as the authentication method used to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="896a6-110">se conecta como la cuenta con la que se ejecuta el servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="896a6-110">Agent connects as the account that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service runs as.</span></span>  
  
 <span data-ttu-id="896a6-111">**Utilizar autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="896a6-111">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="896a6-112">Establece la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como método de autenticación que se utiliza para conectarse a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="896a6-112">Sets [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication as the authentication method used to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="896a6-113">se proporciona por motivos de compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="896a6-113">Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="896a6-114">Para mejorar la seguridad, utilice la autenticación de Windows siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="896a6-114">For improved security, use Windows Authentication if possible.</span></span>  
  
 <span data-ttu-id="896a6-115">**Inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="896a6-115">**Login**</span></span>  
 <span data-ttu-id="896a6-116">Especifica el nombre de inicio de sesión que debe utilizarse para conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="896a6-116">Specifies the login name to use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="896a6-117">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="896a6-117">**Password**</span></span>  
 <span data-ttu-id="896a6-118">Especifica la contraseña que debe utilizarse para conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="896a6-118">Specifies the password to use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
  
