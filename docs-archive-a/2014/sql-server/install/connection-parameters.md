---
title: Parámetros de conexión | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], connections
- authentication [Upgrade Advisor]
- SQL Server Upgrade Advisor, connections
- connections [Upgrade Advisor]
- server instances [Upgrade Advisor]
- default server instances
- analyzing system [Upgrade Advisor], connections
ms.assetid: f754d038-637a-4d8e-85b0-b242e6499d26
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 27eb69dfd2c41710a47861e0992486267f692a3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670778"
---
# <a name="connection-parameters"></a><span data-ttu-id="8bab8-102">Parámetros de conexión</span><span class="sxs-lookup"><span data-stu-id="8bab8-102">Connection Parameters</span></span>
  <span data-ttu-id="8bab8-103">Para analizar ciertos tipos de servidor, como [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], debe seleccionar una instancia concreta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bab8-103">To analyze certain server types, such as the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], you must select a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8bab8-104">La instancia predeterminada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está seleccionada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8bab8-104">The default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is automatically selected.</span></span> <span data-ttu-id="8bab8-105">Puede cambiar la selección o seleccionar una instancia única a la vez para el análisis del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="8bab8-105">You can change this selection, but you can select only one instance at a time for analysis by Upgrade Advisor.</span></span> <span data-ttu-id="8bab8-106">Si ha incluido un tipo de servidor que requiere autenticación, debe escribir el modo de autenticación y las credenciales.</span><span class="sxs-lookup"><span data-stu-id="8bab8-106">If you have included a server type that requires authentication, you must enter the authentication mode and credentials.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8bab8-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="8bab8-107">Options</span></span>  
 <span data-ttu-id="8bab8-108">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="8bab8-108">**Server name**</span></span>  
 <span data-ttu-id="8bab8-109">Se rellena previamente con el nombre de equipo que escribió en el panel Componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bab8-109">Pre-populated with the computer name that you entered in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components pane.</span></span>  
  
 <span data-ttu-id="8bab8-110">**Nombre de instancia**</span><span class="sxs-lookup"><span data-stu-id="8bab8-110">**Instance name**</span></span>  
 <span data-ttu-id="8bab8-111">Seleccione una de las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que están disponibles en el equipo.</span><span class="sxs-lookup"><span data-stu-id="8bab8-111">Select from the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are available on the computer.</span></span> <span data-ttu-id="8bab8-112">Si no aparece una lista de instancias, use MSSQLSERVER para examinar la instancia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8bab8-112">If you do not see a list of instances, use MSSQLSERVER to scan the default instance.</span></span> <span data-ttu-id="8bab8-113">Esto es especialmente interesante para equipos remotos.</span><span class="sxs-lookup"><span data-stu-id="8bab8-113">This is especially relevant for remote computers.</span></span> <span data-ttu-id="8bab8-114">También puede utilizar la palabra "predeterminado" para examinar la instancia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8bab8-114">You can also use the word "default" to scan the default instance.</span></span>  
  
 <span data-ttu-id="8bab8-115">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="8bab8-115">**Authentication**</span></span>  
 <span data-ttu-id="8bab8-116">Seleccione un modo de autenticación de la lista de modos de autenticación disponibles en este equipo.</span><span class="sxs-lookup"><span data-stu-id="8bab8-116">Select from the list of available authentication modes on this computer.</span></span> <span data-ttu-id="8bab8-117">De forma predeterminada, el modo de autenticación es Autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="8bab8-117">By default, the authentication mode is Windows Authentication.</span></span>  
  
 <span data-ttu-id="8bab8-118">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="8bab8-118">**User name**</span></span>  
 <span data-ttu-id="8bab8-119">Si usa la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], escriba un nombre de usuario en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="8bab8-119">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, enter a user name in the box.</span></span> <span data-ttu-id="8bab8-120">Es recomendable que el nombre de usuario tenga credenciales administrativas en este equipo.</span><span class="sxs-lookup"><span data-stu-id="8bab8-120">We recommend that the user name have administrative credentials on the computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8bab8-121">Si selecciona autenticación de Windows, el nombre de usuario del usuario que ha iniciado la sesión actual se rellena en el cuadro de texto **nombre de usuario** .</span><span class="sxs-lookup"><span data-stu-id="8bab8-121">If you select Windows Authentication, the user name of the currently logged-on user is populated in the **User name** text box.</span></span>  
  
 <span data-ttu-id="8bab8-122">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="8bab8-122">**Password**</span></span>  
 <span data-ttu-id="8bab8-123">Escriba la contraseña del usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="8bab8-123">Enter the password for the specified user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bab8-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8bab8-124">See Also</span></span>  
 <span data-ttu-id="8bab8-125">[Trabajar con el asesor de actualizaciones](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="8bab8-125">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="8bab8-126">Referencia de la interfaz de usuario del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="8bab8-126">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
