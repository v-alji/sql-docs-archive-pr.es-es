---
title: Editor del administrador de conexiones con Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelconnection.f1
helpviewer_keywords:
- Excel Connection Manager Editor
ms.assetid: 7ff097e4-cafb-4885-a898-05b2a46628c1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f66de13b710e5ccb577e6f2d67c215572e34767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673796"
---
# <a name="excel-connection-manager-editor"></a><span data-ttu-id="1e88c-102">Editor de Administrador de conexiones con Excel</span><span class="sxs-lookup"><span data-stu-id="1e88c-102">Excel Connection Manager Editor</span></span>
  <span data-ttu-id="1e88c-103">Utilice el cuadro de diálogo **Editor del administrador de conexiones con Excel** para agregar una conexión a un archivo de libro de [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] existente o nuevo.</span><span class="sxs-lookup"><span data-stu-id="1e88c-103">Use the **Excel Connection Manager Editor** dialog box to add a connection to an existing or a new [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook file.</span></span>  
  
 <span data-ttu-id="1e88c-104">Para obtener más información acerca del Administrador de conexiones con Excel, vea [Excel Connection Manager](connection-manager/excel-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1e88c-104">To learn more about the Excel connection manager, see [Excel Connection Manager](connection-manager/excel-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e88c-105">No puede conectar con un archivo de Excel protegido mediante contraseña.</span><span class="sxs-lookup"><span data-stu-id="1e88c-105">You cannot connect to a password-protected Excel file.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1e88c-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="1e88c-106">Options</span></span>  
 <span data-ttu-id="1e88c-107">**Ruta de acceso del archivo Excel**</span><span class="sxs-lookup"><span data-stu-id="1e88c-107">**Excel file path**</span></span>  
 <span data-ttu-id="1e88c-108">Escriba la ruta de acceso y el nombre de archivo de un archivo de libro de Excel (.xls) nuevo o existente.</span><span class="sxs-lookup"><span data-stu-id="1e88c-108">Type the path and file name of an existing or a new Excel workbook file (.xls).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="1e88c-109">El **Editor de destino de Excel** creará automáticamente el archivo de Excel cuando seleccione una **conexión de Excel** que señale a un archivo nuevo o que no existe y, a continuación, haga clic en **nuevo** en **nombre de la hoja de Excel**.</span><span class="sxs-lookup"><span data-stu-id="1e88c-109">The **Excel Destination Editor** automatically creates the Excel file when you select an **Excel Connection** that points to a new/non-existent file and then click **New** for **Name of the Excel Sheet**.</span></span>  
  
 <span data-ttu-id="1e88c-110">**Browse**</span><span class="sxs-lookup"><span data-stu-id="1e88c-110">**Browse**</span></span>  
 <span data-ttu-id="1e88c-111">Utilice el cuadro de diálogo **abrir** para ir a la carpeta en la que se encuentra el archivo de Excel o donde desea crear el nuevo archivo.</span><span class="sxs-lookup"><span data-stu-id="1e88c-111">Use the **Open** dialog box to navigate to the folder in which the excel file exists or where you want to create the new file.</span></span>  
  
 <span data-ttu-id="1e88c-112">**Versión de Excel**</span><span class="sxs-lookup"><span data-stu-id="1e88c-112">**Excel version**</span></span>  
 <span data-ttu-id="1e88c-113">Especifique la versión de Microsoft Excel utilizada para crear el archivo.</span><span class="sxs-lookup"><span data-stu-id="1e88c-113">Specify the version of Microsoft Excel that was used to create the file.</span></span>  
  
|<span data-ttu-id="1e88c-114">Opción</span><span class="sxs-lookup"><span data-stu-id="1e88c-114">Option</span></span>|<span data-ttu-id="1e88c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e88c-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1e88c-116">Excel 97-2003</span><span class="sxs-lookup"><span data-stu-id="1e88c-116">Excel 97-2003</span></span>|<span data-ttu-id="1e88c-117">El archivo se ha creado con Excel 97 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="1e88c-117">File was created using Excel 97 or later.</span></span>|  
|<span data-ttu-id="1e88c-118">Excel 3,0</span><span class="sxs-lookup"><span data-stu-id="1e88c-118">Excel 3.0</span></span>|<span data-ttu-id="1e88c-119">El archivo se creó con Excel 3,0.</span><span class="sxs-lookup"><span data-stu-id="1e88c-119">File was created using Excel 3.0.</span></span>|  
|<span data-ttu-id="1e88c-120">Excel 4,0</span><span class="sxs-lookup"><span data-stu-id="1e88c-120">Excel 4.0</span></span>|<span data-ttu-id="1e88c-121">El archivo se ha creado con Excel 4.0.</span><span class="sxs-lookup"><span data-stu-id="1e88c-121">File was created using Excel 4.0.</span></span>|  
|<span data-ttu-id="1e88c-122">Excel 5,0</span><span class="sxs-lookup"><span data-stu-id="1e88c-122">Excel 5.0</span></span>|<span data-ttu-id="1e88c-123">El archivo se ha creado con Excel 95 (7.0).</span><span class="sxs-lookup"><span data-stu-id="1e88c-123">File was created using Excel 95 (7.0).</span></span>|  
  
 <span data-ttu-id="1e88c-124">**La primera fila tiene nombres de columna**</span><span class="sxs-lookup"><span data-stu-id="1e88c-124">**First row has column names**</span></span>  
 <span data-ttu-id="1e88c-125">Especifique si la primera fila de datos de la hoja seleccionada contiene nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="1e88c-125">Specify whether the first row of data in the selected worksheet contains column names.</span></span> <span data-ttu-id="1e88c-126">El valor predeterminado de esta opción es **True**.</span><span class="sxs-lookup"><span data-stu-id="1e88c-126">The default value of this option is **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e88c-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e88c-127">See Also</span></span>  
 <span data-ttu-id="1e88c-128">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1e88c-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="1e88c-129">Crear bucles entre archivos y tablas de Excel mediante un contenedor de bucles ForEach</span><span class="sxs-lookup"><span data-stu-id="1e88c-129">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
