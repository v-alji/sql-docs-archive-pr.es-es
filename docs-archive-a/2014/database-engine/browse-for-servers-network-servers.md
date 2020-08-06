---
title: Buscar servidores (servidores de redes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.browseservers.network.f1
ms.assetid: a59ffcd6-4b69-4c5c-9740-699ccb2183fb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0ba5e4e5dd6d9a6541a98e0cb30229d7335bac24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674367"
---
# <a name="browse-for-servers-network-servers"></a><span data-ttu-id="07ef0-102">Buscar servidores (Servidores de redes)</span><span class="sxs-lookup"><span data-stu-id="07ef0-102">Browse for Servers (Network Servers)</span></span>
  <span data-ttu-id="07ef0-103">Si se conecta a un componente de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y no conoce el nombre exacto de la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], haga clic en \*\*Buscar más \*\*del cuadro **Nombre del servidor** para abrir el cuadro de diálogo **Buscar servidores**.</span><span class="sxs-lookup"><span data-stu-id="07ef0-103">If you are connecting to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] component and you do not know the exact name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance, click **Browse for more** in the **Server name** box to open the **Browse for Servers** dialog box.</span></span>  
  
 <span data-ttu-id="07ef0-104">Este cuadro de diálogo se rellena con el servicio Explorador de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en los equipos de servidor.</span><span class="sxs-lookup"><span data-stu-id="07ef0-104">This dialog is populated by the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser service on the server computers.</span></span> <span data-ttu-id="07ef0-105">Existen varios motivos por los que es posible que el nombre de una instancia no aparezca en la lista:</span><span class="sxs-lookup"><span data-stu-id="07ef0-105">There are several reasons why the name of an instance might not appear in the list:</span></span>  
  
-   <span data-ttu-id="07ef0-106">Es posible que el servicio Explorador de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no se esté ejecutando en el equipo en el que se ejecuta [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07ef0-106">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser service might not be running on the computer running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="07ef0-107">El puerto UDP 1434 puede estar bloqueado por un firewall.</span><span class="sxs-lookup"><span data-stu-id="07ef0-107">UDP port 1434 might be blocked by a firewall.</span></span>  
  
-   <span data-ttu-id="07ef0-108">Es posible que la marca **HideInstance** esté establecida.</span><span class="sxs-lookup"><span data-stu-id="07ef0-108">The **HideInstance** flag might be set.</span></span>  
  
 <span data-ttu-id="07ef0-109">Para conectarse a una instancia que no aparece en la lista, escriba una cadena de conexión completa para la instancia, incluido el número de puerto TCP/IP o el nombre de canalización de canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="07ef0-109">To connect to an instance that does not appear in the list, type a full connection string for the instance, including the TCP/IP port number or the named pipes pipe name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="07ef0-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="07ef0-110">Options</span></span>  
 <span data-ttu-id="07ef0-111">**Seleccionar una de las instancias de SQL Server de la red para la conexión**</span><span class="sxs-lookup"><span data-stu-id="07ef0-111">**Select a SQL Server instance in the network for your connection**</span></span>  
 <span data-ttu-id="07ef0-112">Indique el servidor con el que desea conectarse, haciendo clic en la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que se muestra en el árbol.</span><span class="sxs-lookup"><span data-stu-id="07ef0-112">Designate the server you want to connect to by clicking on the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance displayed in the tree.</span></span> <span data-ttu-id="07ef0-113">Para mostrar u ocultar partes de la vista de árbol, haga clic en los nodos marcados con un **+** **-** símbolo o.</span><span class="sxs-lookup"><span data-stu-id="07ef0-113">You can show or hide portions of the tree view by clicking on the nodes marked with a **+** or **-** symbol.</span></span>  
  
  
