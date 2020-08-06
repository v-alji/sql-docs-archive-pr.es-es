---
title: Configurar un Firewall para el acceso de FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- Windows Firewall [Database Engine], FILESTREAM
- FILESTREAM [SQL Server], Windows Firewall
ms.assetid: fc52007f-c26f-4f8e-b9d8-55a7978f4d56
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8b787403fefdd336dd82bf7ccb93cdf21fe5a90d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676019"
---
# <a name="configure-a-firewall-for-filestream-access"></a><span data-ttu-id="8fee2-102">Configurar un Firewall para el acceso de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="8fee2-102">Configure a Firewall for FILESTREAM Access</span></span>
  <span data-ttu-id="8fee2-103">Para utilizar FILESTREAM en un entorno protegido mediante firewall, tanto el cliente como el servidor deben poder resolver los nombres DNS en el servidor que contenga los archivos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="8fee2-103">To use FILESTREAM in a firewall-protected environment, both the client and server must be able to resolve DNS names to the server that contains the FILESTREAM files.</span></span> <span data-ttu-id="8fee2-104">FILESTREAM requiere que los puertos 139 y 445 de uso compartido de archivos de Windows estén abiertos.</span><span class="sxs-lookup"><span data-stu-id="8fee2-104">FILESTREAM requires the Windows file-sharing ports 139 and 445 to be open.</span></span>  
  
### <a name="to-open-the-windows-file-sharing-ports-on-a-computer-that-is-running-windows-7"></a><span data-ttu-id="8fee2-105">Para abrir los puertos de uso compartido de archivos de Windows en un equipo que ejecuta Windows 7</span><span class="sxs-lookup"><span data-stu-id="8fee2-105">To open the Windows file-sharing ports on a computer that is running Windows 7</span></span>  
  
1.  <span data-ttu-id="8fee2-106">En el Panel de control, abra **Firewall de Windows**.</span><span class="sxs-lookup"><span data-stu-id="8fee2-106">In Control Panel, open **Windows Firewall**.</span></span>  
  
2.  <span data-ttu-id="8fee2-107">En el panel izquierdo, haga clic en **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="8fee2-107">In the left pane, click **Advanced settings**.</span></span> <span data-ttu-id="8fee2-108">Si se le pide una contraseña de administrador o una confirmación, escriba la contraseña o proporcione la confirmación.</span><span class="sxs-lookup"><span data-stu-id="8fee2-108">If you're prompted for an administrator password or confirmation, type the password or provide confirmation.</span></span>  
  
3.  <span data-ttu-id="8fee2-109">En el cuadro de diálogo **Firewall de Windows con seguridad avanzada** , en el panel izquierdo, haga clic en **Reglas de entrada**y, a continuación, en el panel derecho, haga clic en **Nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="8fee2-109">In the **Windows Firewall with Advanced Security** dialog box, in the left pane, click **Inbound Rules**, and then, in the right pane, click **New Rule**.</span></span>  
  
4.  <span data-ttu-id="8fee2-110">Siga las instrucciones del Asistente para nueva regla de entrada para agregar el puerto TCP 139.</span><span class="sxs-lookup"><span data-stu-id="8fee2-110">Follow the instructions in the New Inbound Rule wizard to add TCP port 139.</span></span>  
  
5.  <span data-ttu-id="8fee2-111">Repita el paso anterior para agregar el puerto TCP 445.</span><span class="sxs-lookup"><span data-stu-id="8fee2-111">Repeat the previous step to add TCP port 445.</span></span>  
  
6.  <span data-ttu-id="8fee2-112">Cierre el cuadro de diálogo de **Firewall de Windows con seguridad avanzada** .</span><span class="sxs-lookup"><span data-stu-id="8fee2-112">Close the **Windows Firewall with Advanced Security** dialog box.</span></span>  
  
  
