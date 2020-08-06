---
title: Progreso del Asesor de actualizaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], analysis progress status
- analyzing system [Upgrade Advisor], progress information
- SQL Server Upgrade Advisor, analysis progress status
- monitoring analysis progress
- progress information [Upgrade Advisor]
- status information [Upgrade Advisor]
ms.assetid: a9e3d1c8-d492-4beb-93c7-f1bc40d4a910
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b504b8f1c8392ad2cf55837dc65bbb2f019d6f48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672406"
---
# <a name="upgrade-advisor-progress"></a><span data-ttu-id="d77e9-102">Progreso del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="d77e9-102">Upgrade Advisor Progress</span></span>
  <span data-ttu-id="d77e9-103">El análisis del Asesor de actualizaciones se inicia con un analizador dedicado que realiza un análisis de cada componente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="d77e9-103">Upgrade Advisor analysis starts with a dedicated analyzer that performs an analysis of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component that you selected.</span></span> <span data-ttu-id="d77e9-104">A medida que se analizan los componentes, el progreso se muestra en el cuadro de diálogo de **progreso** .</span><span class="sxs-lookup"><span data-stu-id="d77e9-104">As components are analyzed, progress is reported in the **Progress** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d77e9-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="d77e9-105">Options</span></span>  
 <span data-ttu-id="d77e9-106">**Acción**</span><span class="sxs-lookup"><span data-stu-id="d77e9-106">**Action**</span></span>  
 <span data-ttu-id="d77e9-107">Especifica el componente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] seleccionado para el análisis.</span><span class="sxs-lookup"><span data-stu-id="d77e9-107">Specifies the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component that is selected for analysis.</span></span>  
  
 <span data-ttu-id="d77e9-108">**Estado**</span><span class="sxs-lookup"><span data-stu-id="d77e9-108">**Status**</span></span>  
 <span data-ttu-id="d77e9-109">Muestra el valor de estado devuelto desde la interfaz de progreso del componente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d77e9-109">Displays the status value returned from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component progress interface.</span></span>  
  
 <span data-ttu-id="d77e9-110">**Message**</span><span class="sxs-lookup"><span data-stu-id="d77e9-110">**Message**</span></span>  
 <span data-ttu-id="d77e9-111">Muestra el mensaje de error o de confirmación que devuelve cada analizador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d77e9-111">Displays error, failure, or success messages returned from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] individual analyzer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d77e9-112">Si el análisis se prolonga demasiado tiempo, puede detenerlo, salir del Asistente para análisis del Asesor de actualizaciones y, a continuación, volver a ejecutar el asistente.</span><span class="sxs-lookup"><span data-stu-id="d77e9-112">If the analysis is taking too long, you can stop the analysis, exit the Upgrade Advisor Analysis Wizard, and then rerun the wizard.</span></span> <span data-ttu-id="d77e9-113">Para reducir el tiempo del análisis, seleccione menos componentes para analizar.</span><span class="sxs-lookup"><span data-stu-id="d77e9-113">To reduce analysis time, select fewer components to scan.</span></span>  
  
 <span data-ttu-id="d77e9-114">Cuando el análisis se haya completado, el informe se escribe en un archivo.</span><span class="sxs-lookup"><span data-stu-id="d77e9-114">When analysis is complete, the report is written to a file.</span></span> <span data-ttu-id="d77e9-115">Puede ver el informe haciendo clic en **iniciar Informe** para iniciar el visor de informes desde esta página.</span><span class="sxs-lookup"><span data-stu-id="d77e9-115">You can view the report by clicking **Launch Report** to launch the report viewer from this page.</span></span> <span data-ttu-id="d77e9-116">Si desea ver el informe más adelante, puede abrir el visor de **informes del Asesor de actualizaciones** desde la página de inicio del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="d77e9-116">If you want to view the report later, you can open the **Upgrade Advisor Report Viewer** from the Upgrade Advisor start page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d77e9-117">Los informes anteriores se guardan cada vez que se analice un servidor.</span><span class="sxs-lookup"><span data-stu-id="d77e9-117">Previous reports are saved every time you analyze a server.</span></span> <span data-ttu-id="d77e9-118">Los informes se guardan con la marca de tiempo como nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="d77e9-118">The reports are saved using the timestamp for the file name.</span></span> <span data-ttu-id="d77e9-119">El visor de informes muestra los cinco últimos informes guardados.</span><span class="sxs-lookup"><span data-stu-id="d77e9-119">The report viewer displays the latest five saved reports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d77e9-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d77e9-120">See Also</span></span>  
 <span data-ttu-id="d77e9-121">[Cómo: iniciar el asesor de actualizaciones](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="d77e9-121">[How to: Launch Upgrade Advisor](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="d77e9-122">[Cómo: ejecutar el Asistente para análisis del Asesor de actualizaciones](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="d77e9-122">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="d77e9-123">[Componentes de SQL Server](../../../2014/sql-server/install/sql-server-components.md) </span><span class="sxs-lookup"><span data-stu-id="d77e9-123">[SQL Server Components](../../../2014/sql-server/install/sql-server-components.md) </span></span>  
 <span data-ttu-id="d77e9-124">[Referencia de la interfaz de usuario del Asesor de actualizaciones](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d77e9-124">[Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span></span>  
 [<span data-ttu-id="d77e9-125">Trabajar con el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="d77e9-125">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
