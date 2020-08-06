---
title: Editor de destino de archivos sin formato (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledestinationconnectionmanager.f1
ms.assetid: a0ec9643-3b44-4467-b855-f45ae4794f7f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a693591921a5669eb9bc8160f0be076ab4d6869b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744754"
---
# <a name="raw-file-destination-editor-connection-manager-page"></a><span data-ttu-id="904ca-102">Editor de destino de archivos sin formato (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="904ca-102">Raw File Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="904ca-103">Use el editor de destino de archivos sin formato para configurar el destino de archivo sin formato con el fin de escribir datos sin formato en un archivo.</span><span class="sxs-lookup"><span data-stu-id="904ca-103">Use the Raw File Destination Editor to configure the Raw File destination to write raw data to a file.</span></span>  
  
 <span data-ttu-id="904ca-104">**¿Qué desea hacer?**</span><span class="sxs-lookup"><span data-stu-id="904ca-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="904ca-105">Abrir el editor de destino de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="904ca-105">Open the Raw File Destination Editor</span></span>](#open)  
  
-   [<span data-ttu-id="904ca-106">Establecer opciones en la pestaña administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="904ca-106">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="904ca-107">Establecer las opciones de la pestaña Columnas</span><span class="sxs-lookup"><span data-stu-id="904ca-107">Set options on the Columns tab</span></span>](#mapping)  
  
##  <a name="open-the-raw-file-destination-editor"></a><a name="open"></a> <span data-ttu-id="904ca-108">Abra el editor de destino de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="904ca-108">Open the Raw File Destination Editor</span></span>  
  
1.  <span data-ttu-id="904ca-109">Agregue el destino de archivo sin formato a un paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="904ca-109">Add the Raw File destination to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="904ca-110">Haga clic con el botón derecho en el componente y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="904ca-110">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a> <span data-ttu-id="904ca-111">Establecer opciones en la pestaña Administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="904ca-111">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="904ca-112">**Modo de acceso**</span><span class="sxs-lookup"><span data-stu-id="904ca-112">**Access mode**</span></span>  
 <span data-ttu-id="904ca-113">Seleccione cómo se especifica el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="904ca-113">Select how the file name is specified.</span></span> <span data-ttu-id="904ca-114">Seleccione **Nombre de archivo** para escribir el nombre de archivo y la ruta de acceso directamente o **Nombre de archivo de la variable** para especificar una variable que contiene el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="904ca-114">Select **File name** to enter the file name and path directly, of **File name from variable** to specify a variable that contains the file name.</span></span>  
  
 <span data-ttu-id="904ca-115">**Nombre de archivo** o **Nombre de variable**</span><span class="sxs-lookup"><span data-stu-id="904ca-115">**File name** or **Variable name**</span></span>  
 <span data-ttu-id="904ca-116">Escriba el nombre y la ruta de acceso del archivo sin formato o seleccione la variable que contiene el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="904ca-116">Enter the name and path of the raw file, or select the variable that contains the file name.</span></span>  
  
 <span data-ttu-id="904ca-117">**Opción de escritura**</span><span class="sxs-lookup"><span data-stu-id="904ca-117">**Write option**</span></span>  
 <span data-ttu-id="904ca-118">Seleccione el método que va a utilizar para crear y escribir en el archivo.</span><span class="sxs-lookup"><span data-stu-id="904ca-118">Select the method used to create and write to the file.</span></span>  
  
 <span data-ttu-id="904ca-119">**Generar un archivo sin formato inicial**</span><span class="sxs-lookup"><span data-stu-id="904ca-119">**Generate initial raw file**</span></span>  
 <span data-ttu-id="904ca-120">Haga clic en el botón para generar un archivo sin formato vacío que contenga solo las columnas (solo archivos de metadatos), sin tener que ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="904ca-120">Click the button to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="904ca-121">El archivo contiene las columnas seleccionadas en la página **Columnas:** del **Editor de destino de archivos sin formato**.</span><span class="sxs-lookup"><span data-stu-id="904ca-121">The file contains the columns that you selected on the **Columns** page of the **Raw File Destination Editor**.</span></span> <span data-ttu-id="904ca-122">Puede designar el origen de archivo sin formato para este archivo que solo tiene metadatos.</span><span class="sxs-lookup"><span data-stu-id="904ca-122">You can point the Raw File source to this metadata-only file.</span></span>  
  
 <span data-ttu-id="904ca-123">Al hacer clic en **Generar archivo sin formato inicial**, aparece un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="904ca-123">When you click **Generate initial raw file**, a message box appears.</span></span> <span data-ttu-id="904ca-124">Haga clic en **Aceptar** para continuar con la creación del archivo.</span><span class="sxs-lookup"><span data-stu-id="904ca-124">Click **OK** to proceed with creating the file.</span></span> <span data-ttu-id="904ca-125">Haga clic en **Cancelar** para seleccionar otra lista de columnas en la página **Columnas:** .</span><span class="sxs-lookup"><span data-stu-id="904ca-125">Click **Cancel** to select a different list of columns on the **Columns** page.</span></span>  
  
##  <a name="set-options-on-the-columns-tab"></a><a name="mapping"></a><span data-ttu-id="904ca-126">Establecer las opciones de la pestaña columnas</span><span class="sxs-lookup"><span data-stu-id="904ca-126">Set options on the Columns tab</span></span>  
 <span data-ttu-id="904ca-127">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="904ca-127">**Available Input Columns**</span></span>  
 <span data-ttu-id="904ca-128">Seleccione una o varias columnas de entrada para escribir en el archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="904ca-128">Select one or more input columns to write to the raw file.</span></span>  
  
 <span data-ttu-id="904ca-129">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="904ca-129">**Input Column**</span></span>  
 <span data-ttu-id="904ca-130">Una columna de entrada se agrega automáticamente a esta tabla cuando se selecciona en **Columnas de entrada disponibles**, o puede seleccionar la columna de entrada directamente en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="904ca-130">An input column is automatically added to this table when you select it under **Available Input Columns**, or you can select the input column directly in this table.</span></span>  
  
 <span data-ttu-id="904ca-131">**Alias de salida**</span><span class="sxs-lookup"><span data-stu-id="904ca-131">**Output Alias**</span></span>  
 <span data-ttu-id="904ca-132">Especifique un nombre alternativo para usarlo en la columna de salida.</span><span class="sxs-lookup"><span data-stu-id="904ca-132">Specify an alternate name to use for the output column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="904ca-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="904ca-133">See Also</span></span>  
 [<span data-ttu-id="904ca-134">Destino de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="904ca-134">Raw File Destination</span></span>](data-flow/raw-file-destination.md)  
  
  
