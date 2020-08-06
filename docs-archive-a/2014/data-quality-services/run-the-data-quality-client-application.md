---
title: Ejecutar la aplicación Data Quality Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.browseforservers.f1
- sql12.dqs.connecttoserver.f1
ms.assetid: 0b2aa202-7ab2-4c9d-b0f1-802588053a1e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 45372ce22fd1b18f0ec13f7a7fd76a369b78dfd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751509"
---
# <a name="run-the-data-quality-client-application"></a><span data-ttu-id="6cdfb-102">Ejecutar la aplicación Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="6cdfb-102">Run the Data Quality Client Application</span></span>
  <span data-ttu-id="6cdfb-103">Puede utilizar [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) ejecutando [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] e iniciando sesión en un [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cdfb-103">You can use [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) by running [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and logging on to a [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6cdfb-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6cdfb-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6cdfb-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6cdfb-105">Prerequisites</span></span>  
 <span data-ttu-id="6cdfb-106">Debe haber completado la instalación del [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] ejecutando el archivo DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="6cdfb-106">You must have completed the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="6cdfb-107">Para obtener más información, vea [Ejecutar DQSInstaller.exe para completar la instalación del servidor de calidad de datos](install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="6cdfb-107">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6cdfb-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6cdfb-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6cdfb-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="6cdfb-109">Permissions</span></span>  
 <span data-ttu-id="6cdfb-110">Para poder iniciar sesión en [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], es necesario disponer de uno de los tres roles de DQS (dqs_administrator, dqs_kb_editor o dqs_kb_operator) en la base de datos DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="6cdfb-110">You must have one of the three DQS roles (dqs_adminstrator, dqs_kb_editor, or dqs_kb_operator) granted on the DQS_MAIN database to be able to log on to [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
##  <a name="run-data-quality-client"></a><a name="Run"></a><span data-ttu-id="6cdfb-111">Ejecutar Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="6cdfb-111">Run Data Quality Client</span></span>  
 <span data-ttu-id="6cdfb-112">Para ejecutar [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] en el equipo en el que se ha instalado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6cdfb-112">To run [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] on the computer where you have installed it, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="6cdfb-113">Haga clic en **Inicio**, seleccione **Todos los programas**, seleccione **[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]**, seleccione **Data Quality Services**y, por último, haga clic en **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="6cdfb-113">Click **Start**, point to **All Programs**, click **[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]**, click **Data Quality Services**, and then click **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="6cdfb-114">En el cuadro de diálogo **Conectar con el servidor**:</span><span class="sxs-lookup"><span data-stu-id="6cdfb-114">In the **Connect to Server** dialog box:</span></span>  
  
    1.  <span data-ttu-id="6cdfb-115">Especifique el servidor al que desea conectar la aplicación [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6cdfb-115">Specify the server that you want to connect the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] application to.</span></span> <span data-ttu-id="6cdfb-116">Seleccione **(LOCAL)** para conectarse con [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="6cdfb-116">Select **(LOCAL)** to connect to [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] on the local computer.</span></span> <span data-ttu-id="6cdfb-117">También puede hacer clic en la flecha abajo y seleccionar **\<Browse network for more servers>** para conectarse a un servidor diferente (o para conectarse al servidor local por nombre).</span><span class="sxs-lookup"><span data-stu-id="6cdfb-117">You can also click the down arrow and select **\<Browse network for more servers>** to connect to a different server (or to connect to the local server by name).</span></span> <span data-ttu-id="6cdfb-118">Se mostrará el cuadro de diálogo **Buscar servidores** .</span><span class="sxs-lookup"><span data-stu-id="6cdfb-118">The **Browse for Servers** dialog box will be displayed.</span></span> <span data-ttu-id="6cdfb-119">Puede seleccionar un servidor en la pestaña **Servidores locales** o en la pestaña **Servidores de redes** .</span><span class="sxs-lookup"><span data-stu-id="6cdfb-119">You can select a server in the **Local Servers** tab or in the **Network Servers** tab.</span></span>  
  
    2.  <span data-ttu-id="6cdfb-120">Si quiere cifrar la transferencia de datos entre [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] y [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], haga clic en **Opciones** y, después, active la casilla **Cifrar conexión**.</span><span class="sxs-lookup"><span data-stu-id="6cdfb-120">If you want to encrypt data transfer between [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], click **Options**, and then select the **Encrypt Connection** check box.</span></span>  
  
3.  <span data-ttu-id="6cdfb-121">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="6cdfb-121">Click **Connect**.</span></span>  
  
 <span data-ttu-id="6cdfb-122">Aparece la página de inicio del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6cdfb-122">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen appears.</span></span> <span data-ttu-id="6cdfb-123">Para más información, vea [Página de inicio del cliente de calidad de datos](../../2014/data-quality-services/data-quality-client-home-screen.md).</span><span class="sxs-lookup"><span data-stu-id="6cdfb-123">For more information, see [Data Quality Client Home Screen](../../2014/data-quality-services/data-quality-client-home-screen.md).</span></span>  
  
  
