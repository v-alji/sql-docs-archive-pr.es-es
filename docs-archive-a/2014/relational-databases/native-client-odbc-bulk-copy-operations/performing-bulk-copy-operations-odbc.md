---
title: Realizar operaciones de copia masiva (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC]
- ODBC, bulk copy operations
- minimally logged operations [SQL Server Native Client]
- bulk copy [ODBC], about bulk copy
ms.assetid: 5c793405-487c-4f52-88b8-0091d529afb3
author: rothja
ms.author: jroth
ms.openlocfilehash: f2647ebca703eab46d7be0e1cfc2490a65384ee6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749825"
---
# <a name="performing-bulk-copy-operations-odbc"></a><span data-ttu-id="31f7e-102">Realizar operaciones de copia masiva (ODBC)</span><span class="sxs-lookup"><span data-stu-id="31f7e-102">Performing Bulk Copy Operations (ODBC)</span></span>
  <span data-ttu-id="31f7e-103">ODBC estándar no admite directamente las operaciones de copia masiva de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31f7e-103">The ODBC standard does not directly support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy operations.</span></span> <span data-ttu-id="31f7e-104">Cuando se conecta a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versión 7.0 o posteriores, el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client admite las funciones de DB-Library que realizan las operaciones de copia masiva de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31f7e-104">When connected to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports the DB-Library functions that perform [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy operations.</span></span> <span data-ttu-id="31f7e-105">Esta extensión específica del controlador proporciona una ruta de acceso sencilla de actualizar para las aplicaciones de DB-Library existentes que usan las funciones de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="31f7e-105">This driver-specific extension provides an easy upgrade path for existing DB-Library applications that use bulk copy functions.</span></span> <span data-ttu-id="31f7e-106">El soporte técnico de copia masiva especializado se encuentra en los archivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="31f7e-106">The specialized bulk copy support is in the following files:</span></span>  
  
-   <span data-ttu-id="31f7e-107">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="31f7e-107">sqlncli.h</span></span>  
  
     <span data-ttu-id="31f7e-108">Incluye prototipos de función y definiciones de constante para las funciones de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="31f7e-108">Includes function prototypes and constant definitions for bulk copy functions.</span></span> <span data-ttu-id="31f7e-109">sqlncli.h debe estar incluido en la aplicación ODBC que realiza las operaciones de copia masiva y encontrarse en la ruta de inclusión de la aplicación cuando se compila.</span><span class="sxs-lookup"><span data-stu-id="31f7e-109">sqlncli.h must be included in the ODBC application performing bulk copy operations and must be in the application's include path when it is compiled.</span></span>  
  
-   <span data-ttu-id="31f7e-110">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="31f7e-110">sqlncli11.lib</span></span>  
  
     <span data-ttu-id="31f7e-111">Debe estar en la ruta de acceso de la biblioteca del vinculador y estar especificado como un archivo que se va a vincular.</span><span class="sxs-lookup"><span data-stu-id="31f7e-111">Must be in the library path of the linker and specified as a file to be linked.</span></span> <span data-ttu-id="31f7e-112">sqlncli11.lib se distribuye con el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="31f7e-112">sqlncli11.lib is distributed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
-   <span data-ttu-id="31f7e-113">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="31f7e-113">sqlncli11.dll</span></span>  
  
     <span data-ttu-id="31f7e-114">Debe estar presente en el momento de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="31f7e-114">Must be present at execution time.</span></span> <span data-ttu-id="31f7e-115">sqlncli11.dll se distribuye con el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="31f7e-115">sqlncli11.dll is distributed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31f7e-116">La función **SQLBulkOperations** de ODBC no tiene ninguna relación con las [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funciones de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="31f7e-116">The ODBC **SQLBulkOperations** function has no relationship to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy functions.</span></span> <span data-ttu-id="31f7e-117">Las aplicaciones deben utilizar las funciones de copia masiva específicas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31f7e-117">Applications must use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific bulk-copy functions to perform bulk copy operations.</span></span>  
  
## <a name="minimally-logging-bulk-copies"></a><span data-ttu-id="31f7e-118">Registrar mínimamente las copias masivas</span><span class="sxs-lookup"><span data-stu-id="31f7e-118">Minimally Logging Bulk Copies</span></span>  
 <span data-ttu-id="31f7e-119">Con el modelo de recuperación completo, todas las operaciones de inserción de filas que se efectúan durante la carga masiva se registran por completo en el registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="31f7e-119">With the Full Recovery model, all row-insert operations performed by bulk load are fully logged in the transaction log.</span></span> <span data-ttu-id="31f7e-120">Cuando la carga es de un gran volumen de datos, esto puede causar que el registro de transacciones se llene rápidamente.</span><span class="sxs-lookup"><span data-stu-id="31f7e-120">For large data loads, this can cause the transaction log to fill rapidly.</span></span> <span data-ttu-id="31f7e-121">Bajo ciertas condiciones, es posible un registro mínimo.</span><span class="sxs-lookup"><span data-stu-id="31f7e-121">Under certain conditions, minimally logging is possible.</span></span> <span data-ttu-id="31f7e-122">El registro mínimo reduce la posibilidad de que una operación de carga masiva llene el espacio del registro y es más eficaz también que el registro completo.</span><span class="sxs-lookup"><span data-stu-id="31f7e-122">Minimal logging reduces the possibility of a bulk load operation filling the log space and is also more efficient than full logging.</span></span>  
  
 <span data-ttu-id="31f7e-123">Para obtener información sobre el uso del registro mínimo, consulte [requisitos previos para el registro mínimo durante la importación en bloque](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md).</span><span class="sxs-lookup"><span data-stu-id="31f7e-123">For information on using minimal logging, see [Prerequisites for Minimal Logging in Bulk Import](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31f7e-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="31f7e-124">Remarks</span></span>  
 <span data-ttu-id="31f7e-125">Al utilizar bcp.exe en [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o posterior, podrían aparecer errores en situaciones donde no había errores en versiones anteriores a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31f7e-125">When using bcp.exe in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later, you might see errors in situations where there were no errors prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="31f7e-126">Esto es porque en las versiones posteriores, bcp.exe no realiza ya la conversión de tipos de datos implícita.</span><span class="sxs-lookup"><span data-stu-id="31f7e-126">This is because in the later versions, bcp.exe no longer performs implicit data type conversion.</span></span> <span data-ttu-id="31f7e-127">En versiones anteriores a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], bcp.exe convertía los datos numéricos al tipo de datos money, si la tabla de destino tenía el tipo de datos money.</span><span class="sxs-lookup"><span data-stu-id="31f7e-127">Prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], bcp.exe converted numeric data to a money data type, if the target table had a money data type.</span></span> <span data-ttu-id="31f7e-128">Sin embargo, en esa situación, bcp.exe simplemente truncaba los campos adicionales.</span><span class="sxs-lookup"><span data-stu-id="31f7e-128">However, in that situation, bcp.exe simply truncated extra fields.</span></span> <span data-ttu-id="31f7e-129">A partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , si los tipos de datos no coinciden entre el archivo y la tabla de destino, bcp.exe producirá un error si hay datos que tendrían que truncarse para ajustarse a la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="31f7e-129">Beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], if data types do not match between the file and the target table, bcp.exe will raise an error if there is any data that would have to be truncated to fit into the target table.</span></span> <span data-ttu-id="31f7e-130">Para resolver este error, corrija los datos para que coincidan con el tipo de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="31f7e-130">To resolve this error, fix the data to match the target data type.</span></span> <span data-ttu-id="31f7e-131">Opcionalmente, utilice bcp.exe desde una versión anterior a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31f7e-131">Optionally, use bcp.exe from a release prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31f7e-132">En esta sección</span><span class="sxs-lookup"><span data-stu-id="31f7e-132">In This Section</span></span>  
  
-   [<span data-ttu-id="31f7e-133">Utilizar archivos de datos y archivos de formato</span><span class="sxs-lookup"><span data-stu-id="31f7e-133">Using Data Files and Format Files</span></span>](using-data-files-and-format-files.md)  
  
-   [<span data-ttu-id="31f7e-134">Copia masiva de variables de programa</span><span class="sxs-lookup"><span data-stu-id="31f7e-134">Bulk Copying from Program Variables</span></span>](bulk-copying-from-program-variables.md)  
  
-   [<span data-ttu-id="31f7e-135">Administrar tamaños de lote de copia masiva</span><span class="sxs-lookup"><span data-stu-id="31f7e-135">Managing Bulk Copy Batch Sizes</span></span>](managing-bulk-copy-batch-sizes.md)  
  
-   [<span data-ttu-id="31f7e-136">Copia masiva de datos de texto e imagen</span><span class="sxs-lookup"><span data-stu-id="31f7e-136">Bulk Copying Text and Image Data</span></span>](bulk-copying-text-and-image-data.md)  
  
-   [<span data-ttu-id="31f7e-137">Convertir un programa de copia masiva de DB-Library a ODBC</span><span class="sxs-lookup"><span data-stu-id="31f7e-137">Converting from DB-Library to ODBC Bulk Copy</span></span>](converting-from-db-library-to-odbc-bulk-copy.md)  
  
## <a name="see-also"></a><span data-ttu-id="31f7e-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31f7e-138">See Also</span></span>  
 <span data-ttu-id="31f7e-139">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="31f7e-139">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="31f7e-140">Importar y exportar datos en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31f7e-140">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](../import-export/bulk-import-and-export-of-data-sql-server.md)  
  
  
