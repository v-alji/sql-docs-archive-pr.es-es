---
title: Parámetros de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine analysis [Upgrade Advisor]
- SQL Server Upgrade Advisor, Database Engine
- Upgrade Advisor [SQL Server], Database Engine
- analyzing system [Upgrade Advisor], Database Engine
ms.assetid: 44a18bfe-e593-47a5-995f-382c01d3f618
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2b885e7616506fd08cae99166cc794dbfb5dac7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747881"
---
# <a name="sql-server-parameters"></a><span data-ttu-id="d73c3-102">Parámetros de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d73c3-102">SQL Server Parameters</span></span>
  <span data-ttu-id="d73c3-103">En esta página, establezca los parámetros que utilizará el analizador para el análisis de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d73c3-103">On this page, set parameters that the analyzer will use for [!INCLUDE[ssDE](../../includes/ssde-md.md)] analysis.</span></span> <span data-ttu-id="d73c3-104">Puede analizar una, varias o todas las bases de datos, analizar archivos de seguimiento que se crearon con [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] y analizar archivos por lotes de SQL.</span><span class="sxs-lookup"><span data-stu-id="d73c3-104">You can analyze one, several, or all databases, analyze trace files that were created by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], and analyze SQL batch files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d73c3-105">Se pueden detectar algunos problemas de actualización solo si envía los archivos de seguimiento o los archivos por lotes de SQL que se van a analizar.</span><span class="sxs-lookup"><span data-stu-id="d73c3-105">Some upgrade issues can be detected only if you submit trace files or SQL batch files to be analyzed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d73c3-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="d73c3-106">Options</span></span>  
 <span data-ttu-id="d73c3-107">**Base(s) de datos a analizar**</span><span class="sxs-lookup"><span data-stu-id="d73c3-107">**Database(s) to analyze**</span></span>  
 <span data-ttu-id="d73c3-108">Para analizar todas las bases de datos, active la casilla **todas las bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="d73c3-108">To analyze all databases, select the **All databases** check box.</span></span> <span data-ttu-id="d73c3-109">Para analizar una selección de bases de datos, active la casilla situada junto a aquellas bases de datos que desee incluir en el análisis.</span><span class="sxs-lookup"><span data-stu-id="d73c3-109">To analyze a selection of databases, select the check box next to each database to include in the scan.</span></span>  
  
 <span data-ttu-id="d73c3-110">**Analizar archivo(s) de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="d73c3-110">**Analyze trace file(s)**</span></span>  
 <span data-ttu-id="d73c3-111">Active esta casilla para analizar los archivos de seguimiento en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="d73c3-111">Select this check box to analyze trace files in the file system.</span></span>  
  
 <span data-ttu-id="d73c3-112">**Ruta de acceso a los archivos de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="d73c3-112">**Path to trace file(s)**</span></span>  
 <span data-ttu-id="d73c3-113">Puede analizar uno o más archivos.</span><span class="sxs-lookup"><span data-stu-id="d73c3-113">You can analyze one or more files.</span></span> <span data-ttu-id="d73c3-114">Puede ir a una ubicación y seleccionar varios archivos, o puede proporcionar varios nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="d73c3-114">You can browse to a location and select multiple files, or you can provide multiple file names.</span></span> <span data-ttu-id="d73c3-115">Utilice la ruta completa de cada archivo, incluya el nombre de éstos y separe las entradas utilizando el carácter de canalización (|).</span><span class="sxs-lookup"><span data-stu-id="d73c3-115">Use the full path name to each file, include the file name, and separate entries by using the pipe character (|).</span></span>  
  
 <span data-ttu-id="d73c3-116">Si habilita **analizar archivos de seguimiento**, **siguiente** se deshabilitará hasta que escriba un nombre de ruta de acceso y un nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="d73c3-116">If you enable **Analyze trace file(s)**, **Next** is disabled until you enter a path name and a file name.</span></span>  
  
 <span data-ttu-id="d73c3-117">**Analizar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] archivos por lotes**</span><span class="sxs-lookup"><span data-stu-id="d73c3-117">**Analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] batch file(s)**</span></span>  
 <span data-ttu-id="d73c3-118">Active esta casilla para analizar los archivos por lotes de [!INCLUDE[tsql](../../includes/tsql-md.md)] del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="d73c3-118">Select this check box to analyze [!INCLUDE[tsql](../../includes/tsql-md.md)] batch files in the file system.</span></span>  
  
 <span data-ttu-id="d73c3-119">**Ruta de acceso a los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] archivos por lotes**</span><span class="sxs-lookup"><span data-stu-id="d73c3-119">**Path to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] batch file(s)**</span></span>  
 <span data-ttu-id="d73c3-120">Puede analizar uno o más archivos por lotes.</span><span class="sxs-lookup"><span data-stu-id="d73c3-120">You can analyze one or more batch files.</span></span> <span data-ttu-id="d73c3-121">Puede ir a una ubicación y seleccionar varios archivos, o puede escribir varios nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="d73c3-121">You can browse to a location and select multiple files, or you can type multiple file names.</span></span> <span data-ttu-id="d73c3-122">Utilice la ruta completa de cada archivo, incluya el nombre de éstos y separe las entradas utilizando el carácter de canalización (|).</span><span class="sxs-lookup"><span data-stu-id="d73c3-122">Use the full path name to each file, include the file name, and separate entries by using the pipe character (|).</span></span>  
  
 <span data-ttu-id="d73c3-123">Si habilita **analizar archivos por lotes de SQL**, el botón **siguiente** estará deshabilitado hasta que escriba un nombre de ruta de acceso y un nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="d73c3-123">If you enable **Analyze SQL batch file(s)**, the **Next** button is disabled until you enter a path name and a file name.</span></span>  
  
 <span data-ttu-id="d73c3-124">**Separador de lotes de SQL**</span><span class="sxs-lookup"><span data-stu-id="d73c3-124">**SQL Batch Separator**</span></span>  
 <span data-ttu-id="d73c3-125">El texto que se utiliza para separar los lotes de las instrucciones de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d73c3-125">The text that is used to separate batches of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="d73c3-126">El valor predeterminado es **Go**.</span><span class="sxs-lookup"><span data-stu-id="d73c3-126">The default value is **GO**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d73c3-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d73c3-127">See Also</span></span>  
 <span data-ttu-id="d73c3-128">[Trabajar con el asesor de actualizaciones](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="d73c3-128">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="d73c3-129">Referencia de la interfaz de usuario del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="d73c3-129">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
