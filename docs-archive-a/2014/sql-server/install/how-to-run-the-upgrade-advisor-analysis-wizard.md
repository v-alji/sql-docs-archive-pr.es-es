---
title: 'Cómo: ejecutar el Asistente para análisis del Asesor de actualizaciones | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor Analysis Wizard
ms.assetid: d7d2a1e2-1179-4c05-9b0f-555b04dd1199
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7c3e5e8a52c3b166b076aedb122e68f860037edf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676837"
---
# <a name="how-to-run-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="0d8c3-102">Procedimientos: Ejecutar el Asistente para análisis del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="0d8c3-102">How to: Run the Upgrade Advisor Analysis Wizard</span></span>
  <span data-ttu-id="0d8c3-103">Puede iniciar el Asistente para análisis del Asesor de actualizaciones desde la página de inicio de este último.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-103">You start the Upgrade Advisor Analysis Wizard from the Upgrade Advisor start page.</span></span> <span data-ttu-id="0d8c3-104">En este tema se describe cómo ejecutar el Asistente para análisis del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-104">This topic describes how to run the Upgrade Advisor Analysis Wizard.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0d8c3-105">Cuando ejecute el Asistente para análisis del Asesor de actualizaciones, el Asesor de actualizaciones guarda los informes en la carpeta predeterminada para informes.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-105">When you run the Upgrade Advisor Analysis Wizard, Upgrade Advisor saves the reports in the default report folder.</span></span> <span data-ttu-id="0d8c3-106">No obstante, el visor de informes solo muestra los cinco últimos informes guardados.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-106">However, the report viewer displays only the five latest saved reports.</span></span> <span data-ttu-id="0d8c3-107">La ubicación predeterminada de los informes es la actualización de mis documentos \\ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Advisor\110\Reports.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-107">The default location for the reports is My Documents\\[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports.</span></span>  
  
### <a name="to-run-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="0d8c3-108">Para ejecutar el Asistente para análisis del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="0d8c3-108">To run the Upgrade Advisor Analysis Wizard</span></span>  
  
1.  <span data-ttu-id="0d8c3-109">En la página de inicio del Asesor de actualizaciones, haga clic en **iniciar el Asistente para análisis del Asesor de actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-109">On the Upgrade Advisor start page, click **Launch Upgrade Advisor Analysis Wizard**.</span></span>  
  
2.  <span data-ttu-id="0d8c3-110">En la página \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componentes\*\* , escriba el nombre del servidor que se va a examinar en el cuadro **nombre del servidor** y, a continuación, haga clic en **detectar**.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-110">On the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components** page, enter the name of the server to scan in the **Server name** box, and then click **Detect**.</span></span> <span data-ttu-id="0d8c3-111">Siga las instrucciones que se detallan a continuación para especificar el nombre del servidor:</span><span class="sxs-lookup"><span data-stu-id="0d8c3-111">Use the following guidelines for the server name:</span></span>  
  
    -   <span data-ttu-id="0d8c3-112">Para examinar instancias no agrupadas, escriba el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-112">To scan nonclustered instances, enter the computer name.</span></span>  
  
    -   <span data-ttu-id="0d8c3-113">Para examinar instancias en clúster, escriba el nombre virtual de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d8c3-113">To scan clustered instances, enter the virtual [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] name.</span></span>  
  
    -   <span data-ttu-id="0d8c3-114">Para examinar los componentes no agrupados que están instalados en un nodo de un clúster, escriba el nombre del nodo.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-114">To scan nonclustered components that are installed on a node of a cluster, enter the node name.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="0d8c3-115">El Asesor de actualizaciones no admite la conexión a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no configurada para usar el puerto estándar (1433) para las conexiones de clientes.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-115">Upgrade Advisor does not support connecting to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is not set to use the standard port (1433) for client connections.</span></span> <span data-ttu-id="0d8c3-116">Si desea establecer una conexión a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que no usa el puerto estándar (1433), cree un alias mediante la dirección IP y el puerto.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-116">If you want to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that does not use the standard port (1433), create an alias using the IP address and the port.</span></span> <span data-ttu-id="0d8c3-117">Para obtener más información sobre cómo configurar los protocolos de cliente y crear un alias para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] las instancias, vea [configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="0d8c3-117">For more information about configuring client protocols and creating an alias for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances, see [Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span></span>  
    >   
    >  <span data-ttu-id="0d8c3-118">Si no tiene [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalado en el equipo en el que está ejecutando el asesor de actualizaciones, haga clic en **Inicio**y, a continuación, en ejecutar `cliconfg` .</span><span class="sxs-lookup"><span data-stu-id="0d8c3-118">If you do not have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on the computer on which you are running Upgrade Advisor, click **Start**, and then run  `cliconfg`.</span></span> <span data-ttu-id="0d8c3-119">Se abrirá el cuadro de diálogo \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herramienta de red de cliente\*\* .</span><span class="sxs-lookup"><span data-stu-id="0d8c3-119">This opens the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Network Utility** dialog box.</span></span> <span data-ttu-id="0d8c3-120">Use la pestaña **alias** para crear el alias.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-120">Use the **Alias** tab to create the alias.</span></span>  
  
3.  <span data-ttu-id="0d8c3-121">Revise la lista de componentes detectados, modifique las selecciones según sea necesario y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-121">Review the list of components detected, modify the selections as necessary, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="0d8c3-122">En la página **parámetros de conexión** , seleccione la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que desea examinar, seleccione el método de autenticación y, si es necesario, escriba la información de nombre de usuario y contraseña y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-122">On the **Connection Parameters** page, select the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you want to scan, select the authentication method and, if necessary, enter user name and password information, and then click **Next**.</span></span>  
  
     <span data-ttu-id="0d8c3-123">El nombre de instancia predeterminado es MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-123">The default instance name is MSSQLSERVER.</span></span>  
  
5.  <span data-ttu-id="0d8c3-124">Para los componentes seleccionados, escriba la información solicitada.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-124">For selected components, enter the requested information.</span></span> <span data-ttu-id="0d8c3-125">Para obtener más información sobre los cuadros de diálogo individuales, vea referencia de la [interfaz de usuario del Asesor de actualizaciones](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span><span class="sxs-lookup"><span data-stu-id="0d8c3-125">For more information about individual dialog boxes, see [Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span></span>  
  
6.  <span data-ttu-id="0d8c3-126">En la página **confirmar configuración del Asesor de actualizaciones** , revise la información que ha escrito.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-126">On the **Confirm Upgrade Advisor Setting** page, review the information that you entered.</span></span> <span data-ttu-id="0d8c3-127">Puede seleccionar \*\*enviar informes a [!INCLUDE[msCoName](../../includes/msconame-md.md)] \*\* si desea enviar el informe de actualización.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-127">You can select **Send reports to [!INCLUDE[msCoName](../../includes/msconame-md.md)]** if you want to submit your upgrade report.</span></span> <span data-ttu-id="0d8c3-128">También puede revisar la directiva de privacidad.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-128">You can also review the privacy policy.</span></span>  
  
7.  <span data-ttu-id="0d8c3-129">Haga clic en **Ejecutar** para analizar la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d8c3-129">Click **Run** to analyze the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
8.  <span data-ttu-id="0d8c3-130">Una vez finalizado el análisis, haga clic en **iniciar Informe** para ver los problemas detectados de la actualización.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-130">When the analysis is finished, click **Launch Report** to view the detected upgrade issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d8c3-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d8c3-131">See Also</span></span>  
 <span data-ttu-id="0d8c3-132">[Cómo: iniciar el asesor de actualizaciones](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="0d8c3-132">[How to: Launch Upgrade Advisor](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="0d8c3-133">[Ejecutar el asesor de actualizaciones &#40;interfaz de usuario&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="0d8c3-133">[Running Upgrade Advisor &#40;User Interface&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span></span>  
 [<span data-ttu-id="0d8c3-134">Trabajar con el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="0d8c3-134">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
