---
title: Conectar al servidor (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connection.login.analysisserver.f1
ms.assetid: 7e277d22-8d4b-422e-8882-7c5dd7a6d915
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b3530f38534e09ef19e77293880129274dfc211b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743629"
---
# <a name="connect-to-server-analysis-services"></a><span data-ttu-id="a4c06-102">Conectar al servidor (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="a4c06-102">Connect to Server (Analysis Services)</span></span>
  <span data-ttu-id="a4c06-103">Use este cuadro de diálogo para ver o especificar opciones cuando se conecte a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4c06-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="a4c06-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="a4c06-104">Options</span></span>  
 <span data-ttu-id="a4c06-105">**Tipo de servidor**</span><span class="sxs-lookup"><span data-stu-id="a4c06-105">**Server type**</span></span>  
 <span data-ttu-id="a4c06-106">Al registrar un servidor desde el Explorador de objetos, seleccione el tipo de servidor al que conectarse: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services o Integration Services.</span><span class="sxs-lookup"><span data-stu-id="a4c06-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="a4c06-107">El resto del cuadro de diálogo muestra simplemente las opciones que se aplican al tipo de servidor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a4c06-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="a4c06-108">Cuando se registra un servidor desde Servidores registrados, el cuadro **Tipo de servidor** es de solo lectura y coincide con el tipo de servidor que se muestra en el componente Servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="a4c06-108">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="a4c06-109">Para registrar un tipo distinto de servidor, seleccione [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services o Integration Services desde la barra de herramientas Servidores registrados antes de comenzar a registrar un servidor nuevo.</span><span class="sxs-lookup"><span data-stu-id="a4c06-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="a4c06-110">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="a4c06-110">**Server name**</span></span>  
 <span data-ttu-id="a4c06-111">Seleccione la instancia de servidor a la que va a conectarse.</span><span class="sxs-lookup"><span data-stu-id="a4c06-111">Select the server instance to connect to.</span></span> <span data-ttu-id="a4c06-112">De forma predeterminada, aparecerá la instancia de servidor a la que se ha conectado por última vez.</span><span class="sxs-lookup"><span data-stu-id="a4c06-112">The server instance last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="a4c06-113">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="a4c06-113">**Authentication**</span></span>  
 <span data-ttu-id="a4c06-114">Cuando se conecta a una instancia de Analysis Services, se admiten los siguientes modos de autenticación: autenticación de [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="a4c06-114">The following authentication modes are supported when connecting to an instance of Analysis Services: [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="a4c06-115">**Modo de autenticación de Windows (autenticación de Windows)**</span><span class="sxs-lookup"><span data-stu-id="a4c06-115">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="a4c06-116">El modo de **autenticación de Windows** permite a un usuario conectarse a través de una cuenta de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="a4c06-116">**Windows Authentication** mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="a4c06-117">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="a4c06-117">**User name**</span></span>  
 <span data-ttu-id="a4c06-118">Esta opción no está disponible en esta versión.</span><span class="sxs-lookup"><span data-stu-id="a4c06-118">This option is not available in this release.</span></span> <span data-ttu-id="a4c06-119">Escriba el nombre de usuario con el que se va a conectar.</span><span class="sxs-lookup"><span data-stu-id="a4c06-119">Enter the user name to connect with.</span></span> <span data-ttu-id="a4c06-120">Esta opción solo está disponible si ha seleccionado la **autenticación de Windows**para conectarse.</span><span class="sxs-lookup"><span data-stu-id="a4c06-120">This option is only available if you have selected to connect using **Windows Authentication**.</span></span>  
  
 <span data-ttu-id="a4c06-121">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="a4c06-121">**Password**</span></span>  
 <span data-ttu-id="a4c06-122">Esta opción no está disponible en esta versión.</span><span class="sxs-lookup"><span data-stu-id="a4c06-122">This option is not available in this release.</span></span> <span data-ttu-id="a4c06-123">Escriba la contraseña del inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="a4c06-123">Enter the password for the login.</span></span> <span data-ttu-id="a4c06-124">Esta opción solo es editable si ha seleccionado la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para conectarse.</span><span class="sxs-lookup"><span data-stu-id="a4c06-124">This option is only editable if you have selected to connect using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="a4c06-125">**Conexión**</span><span class="sxs-lookup"><span data-stu-id="a4c06-125">**Connect**</span></span>  
 <span data-ttu-id="a4c06-126">Haga clic aquí para conectarse al servidor seleccionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a4c06-126">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="a4c06-127">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="a4c06-127">**Options**</span></span>  
 <span data-ttu-id="a4c06-128">Haga clic aquí para que se muestren las opciones adicionales de conexión al servidor, como registrar un servidor y recordar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="a4c06-128">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
