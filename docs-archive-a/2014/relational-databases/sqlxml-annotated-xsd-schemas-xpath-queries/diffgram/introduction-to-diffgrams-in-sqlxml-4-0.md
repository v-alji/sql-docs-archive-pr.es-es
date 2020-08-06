---
title: Introducción a los DiffGrams en SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotations [SQLXML]
- DiffGrams [SQLXML], about DiffGrams
ms.assetid: 1902d67f-baf3-46e6-a36c-b24b5ba6f8ea
author: rothja
ms.author: jroth
ms.openlocfilehash: e57d87d064ace47247f342ed002b162b920e627f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673585"
---
# <a name="introduction-to-diffgrams-in-sqlxml-40"></a><span data-ttu-id="5c33d-102">Introducción a los DiffGrams en SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="5c33d-102">Introduction to DiffGrams in SQLXML 4.0</span></span>
  <span data-ttu-id="5c33d-103">En este tema se ofrece una breve introducción a los DiffGrams.</span><span class="sxs-lookup"><span data-stu-id="5c33d-103">This topic provides a brief introduction to DiffGrams.</span></span>  
  
## <a name="diffgram-format"></a><span data-ttu-id="5c33d-104">Formato de un DiffGram</span><span class="sxs-lookup"><span data-stu-id="5c33d-104">DiffGram Format</span></span>  
 <span data-ttu-id="5c33d-105">Éste es el formato general de un DiffGram:</span><span class="sxs-lookup"><span data-stu-id="5c33d-105">This is the general DiffGram format:</span></span>  
  
```  
<?xml version="1.0"?>  
<diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
   <DataInstance>  
      ...  
   </DataInstance>  
   [<diffgr:before>  
        ...  
   </diffgr:before>]  
  
   [<diffgr:errors>  
        ...  
   </diffgr:errors>]  
</diffgr:diffgram>  
```  
  
 <span data-ttu-id="5c33d-106">El formato de un DiffGram consta de estos bloques:</span><span class="sxs-lookup"><span data-stu-id="5c33d-106">The DiffGram format consists of these blocks:</span></span>  
  
 **\<DataInstance>**  
 <span data-ttu-id="5c33d-107">El nombre de este elemento, **instanceof**, se utiliza con fines explicativos en esta documentación.</span><span class="sxs-lookup"><span data-stu-id="5c33d-107">The name of this element, **DataInstance**, is used for explanation purposes in this documentation.</span></span> <span data-ttu-id="5c33d-108">Por ejemplo, si el DiffGram se generó a partir de un conjunto de elementos en el .NET Framework, el valor de la propiedad **Name** del conjunto de elementos se utilizaría como el nombre de este elemento.</span><span class="sxs-lookup"><span data-stu-id="5c33d-108">For example, if the DiffGram were generated from a dataset in the .NET Framework, the value of the **Name** property of the dataset would be used as the name of this element.</span></span> <span data-ttu-id="5c33d-109">Este bloque contiene todos los datos relevantes tras el cambio, y es posible que incluya incluso los datos que no se han modificado.</span><span class="sxs-lookup"><span data-stu-id="5c33d-109">This block contains all relevant data after the change, possibly including data that has not been modified.</span></span> <span data-ttu-id="5c33d-110">La lógica de procesamiento de DiffGram omite los elementos de este bloque para los que no se especifica el atributo **diffgr: hasChanges** .</span><span class="sxs-lookup"><span data-stu-id="5c33d-110">The DiffGram processing logic ignores the elements in this block for which the **diffgr:hasChanges** attribute is not specified.</span></span>  
  
 **\<diffgr:before>**  
 <span data-ttu-id="5c33d-111">Este bloque opcional contiene las instancias de registro (elementos) originales que deben actualizarse o eliminarse.</span><span class="sxs-lookup"><span data-stu-id="5c33d-111">This optional block contains the original record instances (elements) that must be updated or deleted.</span></span> <span data-ttu-id="5c33d-112">Todas las tablas de base de datos que se van a modificar (actualizar o eliminar) por DiffGram deben aparecer como elementos de nivel superior en el **\<before>** bloque.</span><span class="sxs-lookup"><span data-stu-id="5c33d-112">All the database tables being modified (updated or deleted) by the DiffGram must appear as top-level elements in the **\<before>** block.</span></span>  
  
 **\<diffgr:errors>**  
 <span data-ttu-id="5c33d-113">La lógica de procesamiento de DiffGram omite este bloque opcional.</span><span class="sxs-lookup"><span data-stu-id="5c33d-113">This optional block is ignored by the DiffGram processing logic.</span></span>  
  
## <a name="diffgram-annotations"></a><span data-ttu-id="5c33d-114">Anotaciones de DiffGram</span><span class="sxs-lookup"><span data-stu-id="5c33d-114">DiffGram Annotations</span></span>  
 <span data-ttu-id="5c33d-115">Estas anotaciones se definen en el espacio de nombres de DiffGram **"urn: schemas-microsoft-com: XML-DiffGram-01"**:</span><span class="sxs-lookup"><span data-stu-id="5c33d-115">These annotations are defined in the DiffGram namespace **"urn:schemas-microsoft-com:xml-diffgram-01"**:</span></span>  
  
 <span data-ttu-id="5c33d-116">**identificador**</span><span class="sxs-lookup"><span data-stu-id="5c33d-116">**id**</span></span>  
 <span data-ttu-id="5c33d-117">Este atributo se usa para emparejar los elementos de los **\<before>** **\<DataInstance>** bloques y.</span><span class="sxs-lookup"><span data-stu-id="5c33d-117">This attribute is used to pair the elements in the **\<before>** and the **\<DataInstance>** blocks.</span></span>  
  
 <span data-ttu-id="5c33d-118">**hasChanges**</span><span class="sxs-lookup"><span data-stu-id="5c33d-118">**hasChanges**</span></span>  
 <span data-ttu-id="5c33d-119">En el caso de una operación de inserción o de actualización, el DiffGram debe especificar este atributo con el valor **insertado** o **modificado**.</span><span class="sxs-lookup"><span data-stu-id="5c33d-119">For an insert or an update operation, the DiffGram must specify this attribute with the value **inserted** or **modified**.</span></span> <span data-ttu-id="5c33d-120">Si este atributo no está presente, la lógica de procesamiento omite el elemento correspondiente de en **\<DataInstance>** y no se realiza ninguna actualización.</span><span class="sxs-lookup"><span data-stu-id="5c33d-120">If this attribute is not present, the corresponding element in the **\<DataInstance>** is ignored by the processing logic and no updates are performed.</span></span> <span data-ttu-id="5c33d-121">Para obtener ejemplos de trabajo, vea los [ejemplos de DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5c33d-121">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="5c33d-122">**parentID**</span><span class="sxs-lookup"><span data-stu-id="5c33d-122">**parentID**</span></span>  
 <span data-ttu-id="5c33d-123">Este atributo se usa para especificar las relaciones entre los elementos primarios y secundarios del DiffGram.</span><span class="sxs-lookup"><span data-stu-id="5c33d-123">This attribute is used to specify parent-child relationships among the elements in the DiffGram.</span></span> <span data-ttu-id="5c33d-124">Este atributo solo aparece en el \<before> bloque.</span><span class="sxs-lookup"><span data-stu-id="5c33d-124">This attribute appears only in the \<before> block.</span></span> <span data-ttu-id="5c33d-125">SQLXML lo utiliza cuando aplica actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="5c33d-125">It is used by SQLXML when applying updates.</span></span> <span data-ttu-id="5c33d-126">La relación entre elementos primarios y secundarios se utiliza para determinar el orden en que deben procesarse los elementos del DiffGram.</span><span class="sxs-lookup"><span data-stu-id="5c33d-126">The parent-child relationship is used in determining the order in which the elements in the DiffGram are processed.</span></span>  
  
## <a name="understanding-the-diffgram-processing-logic"></a><span data-ttu-id="5c33d-127">Descripción de la lógica de procesamiento de DiffGram</span><span class="sxs-lookup"><span data-stu-id="5c33d-127">Understanding the DiffGram Processing Logic</span></span>  
 <span data-ttu-id="5c33d-128">La lógica de procesamiento de DiffGram utiliza ciertas reglas para determinar si una operación es una operación de inserción, actualización o eliminación.</span><span class="sxs-lookup"><span data-stu-id="5c33d-128">The DiffGram processing logic uses certain rules to determine whether an operation is an insert, update, or delete operation.</span></span> <span data-ttu-id="5c33d-129">Estas reglas se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="5c33d-129">These rules are described in the following table.</span></span>  
  
|<span data-ttu-id="5c33d-130">Operación</span><span class="sxs-lookup"><span data-stu-id="5c33d-130">Operation</span></span>|<span data-ttu-id="5c33d-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c33d-131">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c33d-132">Insertar</span><span class="sxs-lookup"><span data-stu-id="5c33d-132">Insert</span></span>|<span data-ttu-id="5c33d-133">Un DiffGram indica una operación de inserción cuando aparece un elemento en el **\<DataInstance>** bloque, pero no en el **\<before>** bloque correspondiente, y se especifica el atributo **diffgr: HasChanges** (**diffgr: HasChanges = Inserted**) en el elemento.</span><span class="sxs-lookup"><span data-stu-id="5c33d-133">A DiffGram indicates an insert operation when an element appears in the **\<DataInstance>** block but not in the corresponding **\<before>** block, and the **diffgr:hasChanges** attribute is specified (**diffgr:hasChanges=inserted**) on the element.</span></span> <span data-ttu-id="5c33d-134">En este caso, el DiffGram inserta la instancia de registro especificada en el bloque en **\<DataInstance>** la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5c33d-134">In this case, the DiffGram inserts the record instance that is specified in the **\<DataInstance>** block into the database.</span></span><br /><br /> <span data-ttu-id="5c33d-135">Si no se especifica el atributo **diffgr: hasChanges** , la lógica de procesamiento omite el elemento y no se realiza ninguna inserción.</span><span class="sxs-lookup"><span data-stu-id="5c33d-135">If the **diffgr:hasChanges** attribute is not specified, the element is ignored by the processing logic and no insert is performed.</span></span> <span data-ttu-id="5c33d-136">Para obtener ejemplos de trabajo, vea los [ejemplos de DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5c33d-136">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span>|  
|<span data-ttu-id="5c33d-137">Actualizar</span><span class="sxs-lookup"><span data-stu-id="5c33d-137">Update</span></span>|<span data-ttu-id="5c33d-138">El DiffGram indica una operación de actualización cuando hay un elemento en el \<before> bloque para el que hay un elemento correspondiente en el **\<DataInstance>** bloque (es decir, ambos elementos tienen un atributo **diffgr: ID** con el mismo valor) y el atributo **diffgr: hasChanges** se especifica con el valor **modificado** en el elemento del **\<DataInstance>** bloque.</span><span class="sxs-lookup"><span data-stu-id="5c33d-138">The DiffGram indicates an update operation when there is an element in the \<before> block for which there is a corresponding element in the **\<DataInstance>** block (that is, both elements have a **diffgr:id** attribute with same value) and the **diffgr:hasChanges** attribute is specified with the value **modified** on the element in the **\<DataInstance>** block.</span></span><br /><br /> <span data-ttu-id="5c33d-139">Si el atributo **diffgr: hasChanges** no se especifica en el elemento del **\<DataInstance>** bloque, la lógica de procesamiento devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="5c33d-139">If the **diffgr:hasChanges** attribute is not specified on the element in the **\<DataInstance>** block, an error is returned by the processing logic.</span></span> <span data-ttu-id="5c33d-140">Para obtener ejemplos de trabajo, vea los [ejemplos de DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5c33d-140">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span><br /><br /> <span data-ttu-id="5c33d-141">Si se especifica **diffgr: parentId** en el **\<before>** bloque, la relación de elementos primarios y secundarios que especifica el **parentId** se usa para determinar el orden en que se actualizan los registros.</span><span class="sxs-lookup"><span data-stu-id="5c33d-141">If **diffgr:parentID** is specified in the **\<before>** block, the parent-child relationship of elements that are specified by **parentID** are used in determining the order in which records are updated.</span></span>|  
|<span data-ttu-id="5c33d-142">Eliminar</span><span class="sxs-lookup"><span data-stu-id="5c33d-142">Delete</span></span>|<span data-ttu-id="5c33d-143">Un DiffGram indica una operación de eliminación cuando un elemento aparece en el **\<before>** bloque, pero no en el **\<DataInstance>** bloque correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5c33d-143">A DiffGram indicates a delete operation when an element appears in the **\<before>** block but not in the corresponding **\<DataInstance>** block.</span></span> <span data-ttu-id="5c33d-144">En este caso, el DiffGram elimina la instancia de registro especificada en el **\<before>** bloque de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5c33d-144">In this case, the DiffGram deletes the record instance that is specified in the **\<before>** block from the database.</span></span> <span data-ttu-id="5c33d-145">Para obtener ejemplos de trabajo, vea los [ejemplos de DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5c33d-145">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span><br /><br /> <span data-ttu-id="5c33d-146">Si se especifica **diffgr: parentId** en el **\<before>** bloque, la relación de elementos primarios y secundarios que especifica el **parentId** se usa para determinar el orden en el que se eliminan los registros.</span><span class="sxs-lookup"><span data-stu-id="5c33d-146">If **diffgr:parentID** is specified in the **\<before>** block, the parent-child relationship of elements that are specified by **parentID** are used in determining the order in which records are deleted.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="5c33d-147">No pueden pasarse parámetros a los DiffGrams.</span><span class="sxs-lookup"><span data-stu-id="5c33d-147">Parameters cannot be passed to DiffGrams.</span></span>  
  
  
