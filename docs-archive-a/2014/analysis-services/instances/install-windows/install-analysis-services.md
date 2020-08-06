---
title: Instalar Analysis Services en modo tabular | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: cd6ac80d-b735-4e3e-a024-489f1409ad33
author: minewiskan
ms.author: owend
ms.openlocfilehash: a677fd7770f646067cafb8fedf6d3705ccf2de3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744920"
---
# <a name="install-analysis-services-in-tabular-mode"></a><span data-ttu-id="e2297-102">Instalar Analysis Services en mode tabular</span><span class="sxs-lookup"><span data-stu-id="e2297-102">Install Analysis Services in Tabular Mode</span></span>
  <span data-ttu-id="e2297-103">Si está instalando Analysis Services para usar las nuevas características de modelado tabular, debe instalar Analysis Services en un modo de servidor que admita ese tipo de modelo.</span><span class="sxs-lookup"><span data-stu-id="e2297-103">If you are installing Analysis Services to use the new tabular modeling features, you must install Analysis Services in a server mode that supports that type of model.</span></span> <span data-ttu-id="e2297-104">El modo de servidor es Tabular y se configura durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="e2297-104">The server mode is Tabular, and it is configured during installation.</span></span>  
  
 <span data-ttu-id="e2297-105">Después de instalar el servidor en este modo, puede utilizarlo en soluciones de host que compile en el diseñador de modelos tabular.</span><span class="sxs-lookup"><span data-stu-id="e2297-105">After you install the server in this mode, you can use it host solutions that you build in tabular model designer.</span></span> <span data-ttu-id="e2297-106">Se requiere un servidor de modo tabular si desea que los datos de modelo tabulares accedan a través de la red.</span><span class="sxs-lookup"><span data-stu-id="e2297-106">A tabular mode server is required if you want tabular model data access over the network.</span></span>  
  
 <span data-ttu-id="e2297-107">Puede especificar el modo Tabular en el Asistente para la instalación o en una instalación en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e2297-107">You can specify Tabular mode in the Installation Wizard or in a command line setup.</span></span> <span data-ttu-id="e2297-108">Las siguientes secciones describen cada una de estas opciones.</span><span class="sxs-lookup"><span data-stu-id="e2297-108">The following sections describe each approach.</span></span>  
  
## <a name="installation-wizard"></a><span data-ttu-id="e2297-109">Asistente para instalación</span><span class="sxs-lookup"><span data-stu-id="e2297-109">Installation Wizard</span></span>  
 <span data-ttu-id="e2297-110">La siguiente lista le muestra qué páginas del Asistente para la instalación de SQL Server se utilizan para instalar Analysis Services en modo Tabular:</span><span class="sxs-lookup"><span data-stu-id="e2297-110">The following list shows you which pages in the SQL Server Installation wizard are used to install Analysis Services in Tabular mode:</span></span>  
  
1.  <span data-ttu-id="e2297-111">Seleccione **Analysis Services** en el árbol de características del programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="e2297-111">Select **Analysis Services** from the Feature Tree in Setup.</span></span>  
  
     <span data-ttu-id="e2297-112">![Árbol de características de instalación que muestra Analysis Services](../../../sql-server/install/media/ssas-setupas.gif "Árbol de características de instalación que muestra Analysis Services")</span><span class="sxs-lookup"><span data-stu-id="e2297-112">![Setup feature tree showing Analsyis Services](../../../sql-server/install/media/ssas-setupas.gif "Setup feature tree showing Analsyis Services")</span></span>  
  
2.  <span data-ttu-id="e2297-113">En la página Configuración de Analysis Services, asegúrese de seleccionar **Modo tabular**.</span><span class="sxs-lookup"><span data-stu-id="e2297-113">On the Analysis Services Configuration page, be sure to select **Tabular Mode**.</span></span>  
  
     <span data-ttu-id="e2297-114">![Página de instalación con opciones de configuración de Analysis Services](../../../sql-server/install/media/ssas-setupasconfig.gif "Página de instalación con opciones de configuración de Analysis Services")</span><span class="sxs-lookup"><span data-stu-id="e2297-114">![Setup page with Analysis Services config options](../../../sql-server/install/media/ssas-setupasconfig.gif "Setup page with Analysis Services config options")</span></span>  
  
 <span data-ttu-id="e2297-115">El modo tabular utiliza el motor analítico en memoria xVelocity (VertiPaq), que es el almacenamiento predeterminado para los modelos tabulares que se implementan en Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e2297-115">Tabular mode uses the xVelocity in-memory analytics engine (VertiPaq), which is the default storage for tabular models that you deploy to Analysis Services.</span></span> <span data-ttu-id="e2297-116">Después de implementar las soluciones de modelo tabular en el servidor, puede configurar selectivamente las soluciones tabulares para utilizar el almacenamiento en disco de DirectQuery como una alternativa al almacenamiento enlazado a la memoria.</span><span class="sxs-lookup"><span data-stu-id="e2297-116">After you deploy tabular model solutions to the server, you can selectively configure tabular solutions to use DirectQuery disk storage as an alternative to memory-bound storage.</span></span>  
  
## <a name="command-line-setup"></a><span data-ttu-id="e2297-117">Instalación de línea de Comandos</span><span class="sxs-lookup"><span data-stu-id="e2297-117">Command Line Setup</span></span>  
 <span data-ttu-id="e2297-118">El programa de instalación de SQL Server incluye un nuevo parámetro (`ASSERVERMODE`) que especifica el modo de servidor.</span><span class="sxs-lookup"><span data-stu-id="e2297-118">SQL Server Setup includes a new parameter (`ASSERVERMODE`) that specifies the server mode.</span></span> <span data-ttu-id="e2297-119">En el siguiente ejemplo se muestra una instalación de la línea de comandos que instala Analysis Services en modo de servidor tabular.</span><span class="sxs-lookup"><span data-stu-id="e2297-119">The following example illustrates a command line setup that installs Analysis Services in Tabular server mode.</span></span>  
  
```  
  
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /FEATURES=AS /ASSERVERMODE=TABULAR /INSTANCENAME=ASTabular /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
 <span data-ttu-id="e2297-120">`INSTANCENAME` debe tener menos de 17 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e2297-120">`INSTANCENAME` must be less than 17 characters.</span></span>  
  
 <span data-ttu-id="e2297-121">Todos los valores de cuenta de marcador de posición se deben reemplazar con cuentas y contraseñas válidas.</span><span class="sxs-lookup"><span data-stu-id="e2297-121">All placeholder account values must be replaced with valid accounts and password.</span></span>  
  
 <span data-ttu-id="e2297-122">Las herramientas como SQL Server Management Studio o [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] no se instalan mediante la sintaxis de la línea de comandos de ejemplo que se proporciona.</span><span class="sxs-lookup"><span data-stu-id="e2297-122">Tools such as SQL Server Management Studio or [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] are not installed using the example command line syntax that is provided.</span></span> <span data-ttu-id="e2297-123">Para obtener más información acerca de cómo agregar características, consulte [Install SQL Server 2014 desde el símbolo del sistema](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="e2297-123">For more information about adding features, see [Install SQL Server 2014 from the Command Prompt](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
 <span data-ttu-id="e2297-124">`ASSERVERMODE` distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e2297-124">`ASSERVERMODE` is case-sensitive.</span></span>  <span data-ttu-id="e2297-125">Todos los valores se deben expresar en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="e2297-125">All values must be expressed in upper case.</span></span> <span data-ttu-id="e2297-126">En la tabla siguiente se describen los valores válidos de `ASSERVERMODE`.</span><span class="sxs-lookup"><span data-stu-id="e2297-126">The following table describes the valid values for `ASSERVERMODE`.</span></span>  
  
|<span data-ttu-id="e2297-127">Value</span><span class="sxs-lookup"><span data-stu-id="e2297-127">Value</span></span>|<span data-ttu-id="e2297-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2297-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e2297-129">MULTIDIMENSIONAL</span><span class="sxs-lookup"><span data-stu-id="e2297-129">MULTIDIMENSIONAL</span></span>|<span data-ttu-id="e2297-130">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e2297-130">This is the default value.</span></span> <span data-ttu-id="e2297-131">Si no establece `ASSERVERMODE`, el servidor se instala en modo de servidor multidimensional.</span><span class="sxs-lookup"><span data-stu-id="e2297-131">If you do not set `ASSERVERMODE`, the server is installed in Multidimensional server mode.</span></span>|  
|<span data-ttu-id="e2297-132">POWERPIVOT</span><span class="sxs-lookup"><span data-stu-id="e2297-132">POWERPIVOT</span></span>|<span data-ttu-id="e2297-133">Este valor es opcional.</span><span class="sxs-lookup"><span data-stu-id="e2297-133">This value is optional.</span></span> <span data-ttu-id="e2297-134">En ejercicio, si establece el parámetro `ROLE`, el modo de servidor se establece automáticamente en 1, haciendo que `ASSERVERMODE` sea opcional en una instalación de PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e2297-134">In practice, if you set the `ROLE` parameter, the server mode is automatically set to 1, making `ASSERVERMODE` optional for a PowerPivot for SharePoint installation.</span></span> <span data-ttu-id="e2297-135">Para obtener más información, vea [Install PowerPivot from the Command Prompt](../../../sql-server/install/install-powerpivot-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="e2297-135">For more information, see [Install PowerPivot from the Command Prompt](../../../sql-server/install/install-powerpivot-from-the-command-prompt.md).</span></span>|  
|<span data-ttu-id="e2297-136">TABULAR</span><span class="sxs-lookup"><span data-stu-id="e2297-136">TABULAR</span></span>|<span data-ttu-id="e2297-137">Se requiere este valor si va a instalar Analysis Services en modo tabular utilizando la instalación de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e2297-137">This value is required if you are installing Analysis Services in Tabular mode using command line setup.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2297-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2297-138">See Also</span></span>  
 <span data-ttu-id="e2297-139">[Determinar el modo de servidor de una instancia de Analysis Services](../determine-the-server-mode-of-an-analysis-services-instance.md) </span><span class="sxs-lookup"><span data-stu-id="e2297-139">[Determine the Server Mode of an Analysis Services Instance](../determine-the-server-mode-of-an-analysis-services-instance.md) </span></span>  
 <span data-ttu-id="e2297-140">[Configurar el acceso in-Memory o DirectQuery para una base de datos de modelo tabular](../../tabular-models/enable-directquery-mode-in-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="e2297-140">[Configure In-Memory or DirectQuery Access for a Tabular Model Database](../../tabular-models/enable-directquery-mode-in-ssms.md) </span></span>  
 [<span data-ttu-id="e2297-141">Modelado tabular &#40;&#41;tabular de SSAS</span><span class="sxs-lookup"><span data-stu-id="e2297-141">Tabular Modeling &#40;SSAS Tabular&#41;</span></span>](../../tabular-models/tabular-models-ssas.md)  
  
  
