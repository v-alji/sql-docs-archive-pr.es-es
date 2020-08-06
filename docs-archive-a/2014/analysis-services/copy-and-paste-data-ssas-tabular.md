---
title: Copiar y pegar datos (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.pastepreviewdb.f1
ms.assetid: 2f8d8b3d-810b-4c31-98f2-341015e13da8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30df733377f3cb6f7583d380fbb8e92a0ea69e88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669990"
---
# <a name="copy-and-paste-data-ssas-tabular"></a><span data-ttu-id="73e10-102">Copiar y pegar datos (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="73e10-102">Copy and Paste Data (SSAS Tabular)</span></span>
  <span data-ttu-id="73e10-103">Puede copiar los datos de tabla de las aplicaciones externas y pegarlos en una tabla nueva o en una ya existente en el diseñador de modelos.</span><span class="sxs-lookup"><span data-stu-id="73e10-103">You can copy table data from external applications and paste it into a new or existing table in the model designer.</span></span> <span data-ttu-id="73e10-104">Los datos que pega del Portapapeles deben estar en formato HTML, como los datos que se copian de Excel o Word.</span><span class="sxs-lookup"><span data-stu-id="73e10-104">The data that you paste from the Clipboard must be in HTML format, for example, data that is copied from Excel or Word.</span></span> <span data-ttu-id="73e10-105">El diseñador de modelos detectará y aplicará automáticamente tipos de datos a los datos pegados.</span><span class="sxs-lookup"><span data-stu-id="73e10-105">The model designer will automatically detect and apply data types to the pasted data.</span></span> <span data-ttu-id="73e10-106">También puede modificar el tipo de datos o el formato para mostrar de una columna de forma manual.</span><span class="sxs-lookup"><span data-stu-id="73e10-106">You can also manually modify the data type or display formatting of a column.</span></span>  
  
 <span data-ttu-id="73e10-107">A diferencia de las tablas con una conexión de origen de datos, las tablas pegadas no tienen una propiedad de nombre de conexión o de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="73e10-107">Unlike tables with a data source connection, pasted tables do not have a Connection Name or Source Data property.</span></span> <span data-ttu-id="73e10-108">Los datos pegados se guardan en el archivo Model.bim.</span><span class="sxs-lookup"><span data-stu-id="73e10-108">Pasted data is persisted in the Model.bim file.</span></span> <span data-ttu-id="73e10-109">Los datos pegados se guardan junto con el proyecto o el archivo Model.bim.</span><span class="sxs-lookup"><span data-stu-id="73e10-109">When the project or Model.bim file is saved, the pasted data is also saved.</span></span>  
  
 <span data-ttu-id="73e10-110">Al implementar un modelo, los datos pegados también se implementan con él, independientemente de si el modelo se procesa con la implementación.</span><span class="sxs-lookup"><span data-stu-id="73e10-110">When a model is deployed, pasted data will also be deployed with it regardless if the model is processed with the deployment.</span></span>  
  
 <span data-ttu-id="73e10-111">Secciones de este tema:</span><span class="sxs-lookup"><span data-stu-id="73e10-111">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="73e10-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="73e10-112">Prerequisites</span></span>](#bkmk_prerequisites)  
  
-   [<span data-ttu-id="73e10-113">Pegar datos</span><span class="sxs-lookup"><span data-stu-id="73e10-113">Paste Data</span></span>](#bkmk_paste_data)  
  
-   [<span data-ttu-id="73e10-114">Cuadro de diálogo Vista previa de pegado</span><span class="sxs-lookup"><span data-stu-id="73e10-114">Paste Preview Dialog Box</span></span>](#bkmk_paste_preview)  
  
##  <a name="prerequisites"></a><a name="bkmk_prerequisites"></a> <span data-ttu-id="73e10-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="73e10-115">Prerequisites</span></span>  
 <span data-ttu-id="73e10-116">Hay algunas restricciones al pegar los datos:</span><span class="sxs-lookup"><span data-stu-id="73e10-116">There are some restrictions when pasting data:</span></span>  
  
-   <span data-ttu-id="73e10-117">Las tablas pegadas no pueden tener más de 10.000 filas.</span><span class="sxs-lookup"><span data-stu-id="73e10-117">Pasted tables cannot have more than 10,000 rows.</span></span>  
  
-   <span data-ttu-id="73e10-118">Las tablas pegadas no deben estar particionadas.</span><span class="sxs-lookup"><span data-stu-id="73e10-118">Pasted tables cannot be partitioned.</span></span>  
  
-   <span data-ttu-id="73e10-119">Las tablas pegadas no se admiten en el modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="73e10-119">Pasted tables are not supported in DirectQuery mode.</span></span>  
  
-   <span data-ttu-id="73e10-120">Las opciones **Pegar y anexar** y **Pegar y reemplazar** solo están disponibles al trabajar con una tabla que se creó inicialmente pegando datos del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="73e10-120">The **Paste Append** and **Paste Replace** options are only available when working with a table that was initially created by pasting data from the Clipboard.</span></span> <span data-ttu-id="73e10-121">No se puede usar **Pegar datos anexados** ni **Pegar datos reemplazados** al agregar datos a una tabla de datos importados de otro tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="73e10-121">You cannot use **Paste Append** or **Paste Replace** to add data into a table of imported data from another type of data source.</span></span>  
  
-   <span data-ttu-id="73e10-122">Al usar **Pegar datos anexados** o **Pegar datos reemplazados**, los nuevos datos deben contener exactamente el mismo número de columnas que los originales.</span><span class="sxs-lookup"><span data-stu-id="73e10-122">When you use **Paste Append** or **Paste Replace**, the new data must contain exactly the same number of columns as the original data.</span></span> <span data-ttu-id="73e10-123">Si es posible, las columnas de datos que se pegan o anexan también deberían ser de los mismos tipos de datos que los de la tabla de destino, o ser de un tipo de datos compatible.</span><span class="sxs-lookup"><span data-stu-id="73e10-123">Preferably, the columns of data that you paste or append should also be of the same or compatible data type as those in the destination table.</span></span> <span data-ttu-id="73e10-124">En algunos casos puede usar un tipo de datos diferente, pero es posible que se muestre un error de **coincidencia de tipos** .</span><span class="sxs-lookup"><span data-stu-id="73e10-124">In some cases you can use a different data type, but a **Type mismatch** error may be displayed.</span></span>  
  
##  <a name="paste-data"></a><a name="bkmk_paste_data"></a> <span data-ttu-id="73e10-125">Pegar datos</span><span class="sxs-lookup"><span data-stu-id="73e10-125">Paste Data</span></span>  
  
#### <a name="to-paste-data-into-the-designer"></a><span data-ttu-id="73e10-126">Para pegar datos en el diseñador</span><span class="sxs-lookup"><span data-stu-id="73e10-126">To paste data into the designer</span></span>  
  
-   <span data-ttu-id="73e10-127">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], haga clic en el menú **Editar** y, a continuación, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="73e10-127">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Edit** menu, and then clicke of the following:</span></span>  
  
    -   <span data-ttu-id="73e10-128">Haga clic en **Pegar** para pegar el contenido del Portapapeles en una tabla nueva.</span><span class="sxs-lookup"><span data-stu-id="73e10-128">Click **Paste** to paste the contents of the Clipboard into a new table.</span></span>  
  
    -   <span data-ttu-id="73e10-129">Haga clic en **Pegar datos anexados** para pegar el contenido del Portapapeles como filas adicionales en la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="73e10-129">Click **Paste Append** to paste the contents of the Clipboard as additional rows into the selected table.</span></span> <span data-ttu-id="73e10-130">Las nuevas filas se agregarán al final de la tabla.</span><span class="sxs-lookup"><span data-stu-id="73e10-130">The new rows will be added to the end of the table.</span></span>  
  
    -   <span data-ttu-id="73e10-131">Haga clic en **Pegar datos reemplazados** para reemplazar la tabla seleccionada con el contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="73e10-131">Click **Paste Replace** to replace the selected table with the contents of the Clipboard.</span></span> <span data-ttu-id="73e10-132">Todos los nombres de encabezado de columna existentes permanecerán en la tabla y se conservarán las relaciones.</span><span class="sxs-lookup"><span data-stu-id="73e10-132">All existing column header names will remain in the table, and relationships are preserved.</span></span>  
  
##  <a name="paste-preview-dialog-box"></a><a name="bkmk_paste_preview"></a><span data-ttu-id="73e10-133">Cuadro de diálogo vista previa de pegado</span><span class="sxs-lookup"><span data-stu-id="73e10-133">Paste Preview Dialog Box</span></span>  
 <span data-ttu-id="73e10-134">El cuadro de diálogo **Vista previa de pegado** le permite ver una vista previa de los datos que se copian en la ventana del diseñador y asegurarse de que se copian correctamente.</span><span class="sxs-lookup"><span data-stu-id="73e10-134">The **Paste Preview** dialog box enables you to see a preview of data that is copied into the designer window and to ensure that the data is copied correctly.</span></span> <span data-ttu-id="73e10-135">Para obtener acceso a este cuadro de diálogo, copie datos basados en tabla en formato HTML en el diseñador, haga clic en el menú **Editar** y, después, en **Pegar**, **Pegar y anexar**o **Pegar y reemplazar**.</span><span class="sxs-lookup"><span data-stu-id="73e10-135">To access this dialog box, copy table-based data in the HTML format to the clipboard, and then in the designer, click on the **Edit** menu, and then click **Paste**, **Paste Append**, or **Paste Replace**.</span></span> <span data-ttu-id="73e10-136">Las opciones **Pegar y anexar** y **Pegar y reemplazar** solo están disponibles al agregar o reemplazar datos en una tabla creada copiando y pegando mediante el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="73e10-136">The **Paste Append** and **Paste Replace** options are only available when you add or replace data in a table that was created by copying and pasting from the Clipboard.</span></span> <span data-ttu-id="73e10-137">No se puede usar **Pegar y anexar** ni **Pegar y reemplazar** para agregar datos en una tabla de datos importados.</span><span class="sxs-lookup"><span data-stu-id="73e10-137">You cannot use **Paste Append** or **Paste Replace** to add data into a table of imported data.</span></span>  
  
 <span data-ttu-id="73e10-138">Las opciones de este cuadro de diálogo son diferentes en función de que los datos se peguen en una tabla completamente nueva, en una tabla existente y reemplacen a los datos existentes, o se agreguen al final de una tabla existente.</span><span class="sxs-lookup"><span data-stu-id="73e10-138">The options for this dialog box are different depending on whether you paste data into a completely new table, paste data into an existing table and then replace the existing data with the new data, or whether you append data to an existing table.</span></span>  
  
### <a name="paste-to-new-table"></a><span data-ttu-id="73e10-139">Pegar en una nueva tabla</span><span class="sxs-lookup"><span data-stu-id="73e10-139">Paste to New Table</span></span>  
 <span data-ttu-id="73e10-140">**Nombre de la tabla**</span><span class="sxs-lookup"><span data-stu-id="73e10-140">**Table name**</span></span>  
 <span data-ttu-id="73e10-141">Especifique el nombre de la tabla que se creará en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="73e10-141">Specify the name of the table that will be created in the designer.</span></span>  
  
 <span data-ttu-id="73e10-142">**Datos que se van a pegar**</span><span class="sxs-lookup"><span data-stu-id="73e10-142">**Data to be pasted**</span></span>  
 <span data-ttu-id="73e10-143">Muestra un ejemplo del contenido del Portapapeles que se agregará a la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="73e10-143">Shows a sample of the Clipboard contents that will be added to the destination table.</span></span>  
  
### <a name="paste-append"></a><span data-ttu-id="73e10-144">Pegar y anexar</span><span class="sxs-lookup"><span data-stu-id="73e10-144">Paste Append</span></span>  
 <span data-ttu-id="73e10-145">**Datos existentes en la tabla**</span><span class="sxs-lookup"><span data-stu-id="73e10-145">**Existing data in the table**</span></span>  
 <span data-ttu-id="73e10-146">Muestra un ejemplo de los datos existentes en la tabla para que pueda comprobar las columnas, tipos de datos, etc.</span><span class="sxs-lookup"><span data-stu-id="73e10-146">Shows a sample of the existing data in the table so that you can verify the columns, data types, etc.</span></span>  
  
 <span data-ttu-id="73e10-147">**Datos que se van a pegar**</span><span class="sxs-lookup"><span data-stu-id="73e10-147">**Data to be pasted**</span></span>  
 <span data-ttu-id="73e10-148">Muestra un ejemplo del contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="73e10-148">Shows a sample of the Clipboard contents.</span></span> <span data-ttu-id="73e10-149">Estos datos se anexarán a los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="73e10-149">The existing data will be appended by this data.</span></span>  
  
### <a name="paste-replace"></a><span data-ttu-id="73e10-150">Pegar y reemplazar</span><span class="sxs-lookup"><span data-stu-id="73e10-150">Paste Replace</span></span>  
 <span data-ttu-id="73e10-151">**Datos existentes en la tabla**</span><span class="sxs-lookup"><span data-stu-id="73e10-151">**Existing data in the table**</span></span>  
 <span data-ttu-id="73e10-152">Muestra un ejemplo de los datos existentes en la tabla para que pueda comprobar las columnas, tipos de datos, etc.</span><span class="sxs-lookup"><span data-stu-id="73e10-152">Shows a sample of the existing data in the table so that you can verify the columns, data types, etc.</span></span>  
  
 <span data-ttu-id="73e10-153">**Datos que se van a pegar**</span><span class="sxs-lookup"><span data-stu-id="73e10-153">**Data to be pasted**</span></span>  
 <span data-ttu-id="73e10-154">Muestra un ejemplo del contenido del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="73e10-154">Shows a sample of the Clipboard contents.</span></span> <span data-ttu-id="73e10-155">Se eliminarán los datos existentes en la tabla de destino y se incrustarán las nuevas filas en la tabla.</span><span class="sxs-lookup"><span data-stu-id="73e10-155">The existing data in the destination table will be deleted and the new rows will be inserted into the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e10-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73e10-156">See Also</span></span>  
 <span data-ttu-id="73e10-157">[Importar datos &#40;&#41;tabular de SSAS](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="73e10-157">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="73e10-158">[Orígenes de datos admitidos &#40;SSAS tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="73e10-158">[Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="73e10-159">Establecer el tipo de datos de una columna &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="73e10-159">Set the Data Type of a Column &#40;SSAS Tabular&#41;</span></span>](tabular-models/set-the-data-type-of-a-column-ssas-tabular.md)  
  
  
