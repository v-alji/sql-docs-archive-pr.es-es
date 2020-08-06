---
title: Instalando el asesor de actualizaciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Setup [Upgrade Advisor]
- Upgrade Advisor [SQL Server], installing
ms.assetid: 1b7d6eca-1df1-47df-bbba-0fc485706a95
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 40f214b01f3e2066708a060c5f3ad1e8aa4a0a23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744981"
---
# <a name="installing-upgrade-advisor"></a><span data-ttu-id="9129f-102">Instalar el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="9129f-102">Installing Upgrade Advisor</span></span>
  <span data-ttu-id="9129f-103">La ubicación en la que instala el Asesor de actualizaciones de SQL Server 2014 depende de lo que vaya a analizar.</span><span class="sxs-lookup"><span data-stu-id="9129f-103">Where you install SQL Server 2014 Upgrade Advisor depends on what you will be analyzing.</span></span> <span data-ttu-id="9129f-104">El Asesor de actualizaciones admite el análisis remoto de todos los componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , excepto [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9129f-104">Upgrade Advisor supports remote analysis of all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="9129f-105">Si no está analizando instancias de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], puede instalar el Asesor de actualizaciones en cualquier equipo que pueda conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]y que cumpla con los [Upgrade Advisor Prerequisites](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="9129f-105">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and that meets the [Upgrade Advisor Prerequisites](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md).</span></span> <span data-ttu-id="9129f-106">Si está examinando instancias de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], debe instalar el Asesor de actualizaciones en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="9129f-106">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="9129f-107">Ejecute el archivo **SQLUA.msi** para instalar el Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="9129f-107">Run the **SQLUA.msi** file to install Upgrade Advisor.</span></span> <span data-ttu-id="9129f-108">Puede instalarlo desde el símbolo del sistema para las instalaciones desatendidas y automatizadas.</span><span class="sxs-lookup"><span data-stu-id="9129f-108">You can install from the command prompt for unattended and automated installations.</span></span> <span data-ttu-id="9129f-109">Vea [Installing Upgrade Advisor from the Command Prompt](../../../2014/sql-server/install/installing-upgrade-advisor-from-the-command-prompt.md) para la sintaxis y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9129f-109">See [Installing Upgrade Advisor from the Command Prompt](../../../2014/sql-server/install/installing-upgrade-advisor-from-the-command-prompt.md) for syntax and examples.</span></span>  
  
 <span data-ttu-id="9129f-110">Obtener SQLUA.msi:</span><span class="sxs-lookup"><span data-stu-id="9129f-110">Get SQLUA.msi:</span></span>  
  
-   <span data-ttu-id="9129f-111">En la carpeta **redist** del soporte del producto [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9129f-111">In the **redist** folder of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] product media.</span></span>  
  
-   <span data-ttu-id="9129f-112">Como parte de la [descarga SQL 2014 Feature Pack](https://www.microsoft.com/download/details.aspx?id=42295).</span><span class="sxs-lookup"><span data-stu-id="9129f-112">As part of the [SQL 2014 Feature Pack download](https://www.microsoft.com/download/details.aspx?id=42295).</span></span>  
  
## <a name="uninstalling-upgrade-advisor"></a><span data-ttu-id="9129f-113">Desinstalar el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="9129f-113">Uninstalling Upgrade Advisor</span></span>  
 <span data-ttu-id="9129f-114">Puede desinstalar el Asesor de actualizaciones mediante **Agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="9129f-114">You can uninstall Upgrade Advisor by using **Add or Remove Programs**.</span></span> <span data-ttu-id="9129f-115">La sintaxis del símbolo del sistema también admite la eliminación o desinstalación.</span><span class="sxs-lookup"><span data-stu-id="9129f-115">The command prompt syntax also supports removal/uninstall.</span></span>  
  
  
