---
title: Crear un rol definido por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c4128993-2333-48c7-84b1-e51cdcea393d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0ee905c2636e20315c2180a6be8f8e40f76d5f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671607"
---
# <a name="create-a-user-defined-role"></a><span data-ttu-id="2d666-102">Crear un rol definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="2d666-102">Create a User-Defined Role</span></span>
    
### <a name="to-create-a-user-defined-role"></a><span data-ttu-id="2d666-103">Para crear un rol definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="2d666-103">To create a user-defined role</span></span>  
  
1.  <span data-ttu-id="2d666-104">Abra [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d666-104">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="2d666-105">Haga clic en **Explorador de objetos** , en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="2d666-105">Click **Object Explorer** on the **View** menu.</span></span>  
  
3.  <span data-ttu-id="2d666-106">En la barra de herramientas del Explorador de objetos, haga clic en **Conectar**y, a continuación, en **Motor de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="2d666-106">On the Object Explorer toolbar, click **Connect**, and then click **Database Engine**.</span></span>  
  
4.  <span data-ttu-id="2d666-107">En el cuadro de diálogo **Conectar al servidor** , indique el nombre del servidor y seleccione un modo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="2d666-107">In the **Connect to Server** dialog box, provide a server name and select an authentication mode.</span></span> <span data-ttu-id="2d666-108">Puede utilizar un punto (.), (local) o `localhost` para indicar el servidor local.</span><span class="sxs-lookup"><span data-stu-id="2d666-108">You can use a period (.), (local), or `localhost` to indicate the local server.</span></span>  
  
5.  <span data-ttu-id="2d666-109">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="2d666-109">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="2d666-110">Expanda Bases de datos, Bases de datos del sistema, msdb, Seguridad y Roles.</span><span class="sxs-lookup"><span data-stu-id="2d666-110">Expand Databases, System Databases, msdb, Security, and Roles.</span></span>  
  
7.  <span data-ttu-id="2d666-111">En el nodo Roles, haga clic con el botón derecho en Roles de base de datos y, luego, haga clic en **Nuevo rol de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="2d666-111">In the Roles node, right-click Database Roles, and click **New Database Role**.</span></span>  
  
8.  <span data-ttu-id="2d666-112">En la página General, indique un nombre y si lo desea, especifique un propietario, esquemas de propiedad y agregue miembros de roles.</span><span class="sxs-lookup"><span data-stu-id="2d666-112">On the General page, provide a name and optionally, specify an owner and owned schemas and add role members.</span></span>  
  
9. <span data-ttu-id="2d666-113">Opcionalmente, haga clic en **Permisos** y configure permisos de objetos.</span><span class="sxs-lookup"><span data-stu-id="2d666-113">Optionally, click **Permissions** and configure object permissions.</span></span>  
  
10. <span data-ttu-id="2d666-114">Opcionalmente, haga clic en **Propiedades extendidas** y configure las propiedades extendidas.</span><span class="sxs-lookup"><span data-stu-id="2d666-114">Optionally, click **Extended Properties** and configure any extended properties.</span></span>  
  
11. <span data-ttu-id="2d666-115">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d666-115">Click **OK**.</span></span>  
  
  
