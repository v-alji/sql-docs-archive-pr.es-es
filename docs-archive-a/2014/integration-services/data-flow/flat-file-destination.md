---
title: Destino de archivo plano | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfiledest.f1
helpviewer_keywords:
- flat files
- Flat File destination
- text file writing [Integration Services]
- destinations [Integration Services], Flat File
ms.assetid: e0d6e356-8db4-48aa-ba66-029397f98f61
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a961b7528b13a4eaa3297343e91f1deaf2fa3226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751317"
---
# <a name="flat-file-destination"></a><span data-ttu-id="64e22-102">Destino de archivo plano</span><span class="sxs-lookup"><span data-stu-id="64e22-102">Flat File Destination</span></span>
  <span data-ttu-id="64e22-103">El destino de archivo plano escribe datos en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="64e22-103">The Flat File destination writes data to a text file.</span></span> <span data-ttu-id="64e22-104">El archivo de texto puede tener formato delimitado, de ancho fijo, de ancho fijo con delimitador de filas o desigual a la derecha.</span><span class="sxs-lookup"><span data-stu-id="64e22-104">The text file can be in delimited, fixed width, fixed width with row delimiter, or ragged right format.</span></span>  
  
 <span data-ttu-id="64e22-105">Puede configurar el destino de archivo plano de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="64e22-105">You can configure the Flat File destination in the following ways:</span></span>  
  
-   <span data-ttu-id="64e22-106">Proporcionar un bloque de texto que se inserta en el archivo antes de escribir cualquier dato.</span><span class="sxs-lookup"><span data-stu-id="64e22-106">Provide a block of text that is inserted in the file before any data is written.</span></span> <span data-ttu-id="64e22-107">El texto puede proporcionar información tal como encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="64e22-107">The text can provide information such as column headings.</span></span>  
  
-   <span data-ttu-id="64e22-108">Especificar si se deben sobrescribir datos en un archivo de destino que tenga el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="64e22-108">Specify whether to overwrite a data in a destination file that has the same name.</span></span>  
  
 <span data-ttu-id="64e22-109">Este destino utiliza un administrador de conexiones de archivos planos para tener acceso al archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="64e22-109">This destination uses a Flat File connection manager to access the text file.</span></span> <span data-ttu-id="64e22-110">Al establecer propiedades en el administrador de conexiones de archivos planos que usa el destino de archivo plano, puede especificar la manera en que el destino de archivo plano establece el formato y escribe el archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="64e22-110">By setting properties on the Flat File connection manager that the Flat File destination uses, you can specify how the Flat File destination formats and writes the text file.</span></span> <span data-ttu-id="64e22-111">Al configurar el administrador de conexiones de archivos planos, se especifica información sobre el archivo y sobre cada columna del archivo.</span><span class="sxs-lookup"><span data-stu-id="64e22-111">When you configure the Flat File connection manager, you specify information about the file and about each column in the file.</span></span> <span data-ttu-id="64e22-112">Por ejemplo, puede especificar los caracteres que delimitan columnas y filas en el archivo, así como el tipo de datos y la longitud de cada columna.</span><span class="sxs-lookup"><span data-stu-id="64e22-112">For example, you specify the characters that delimit columns and rows in the file, and you specify the data type and the length of each column.</span></span> <span data-ttu-id="64e22-113">Para más información, consulte [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="64e22-113">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="64e22-114">El destino de archivo plano incluye la propiedad personalizada Header.</span><span class="sxs-lookup"><span data-stu-id="64e22-114">The Flat File destination includes the Header custom property.</span></span> <span data-ttu-id="64e22-115">Esta propiedad se puede actualizar a través de una expresión de propiedad, al cargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="64e22-115">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="64e22-116">Para más información, vea [Expresiones de Integration Services &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md), [Usar expresiones de propiedad en paquetes](../expressions/use-property-expressions-in-packages.md) y [Propiedades personalizadas de archivo plano](flat-file-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="64e22-116">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md), and [Flat File Custom Properties](flat-file-custom-properties.md).</span></span>  
  
 <span data-ttu-id="64e22-117">Este destino tiene una salida.</span><span class="sxs-lookup"><span data-stu-id="64e22-117">This destination has one output.</span></span> <span data-ttu-id="64e22-118">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="64e22-118">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-flat-file-destination"></a><span data-ttu-id="64e22-119">Configuración del destino de archivo plano</span><span class="sxs-lookup"><span data-stu-id="64e22-119">Configuration of the Flat File Destination</span></span>  
 <span data-ttu-id="64e22-120">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="64e22-120">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="64e22-121">Para obtener más información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de origen de archivos planos** , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="64e22-121">For more information about the properties that you can set in the **Flat File Source Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="64e22-122">Editor de destino de archivos planos &#40;página Administrador de conexiones&#41;</span><span class="sxs-lookup"><span data-stu-id="64e22-122">Flat File Destination Editor &#40;Connection Manager Page&#41;</span></span>](../flat-file-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="64e22-123">Editor de destino de archivos planos &#40;página Asignaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="64e22-123">Flat File Destination Editor &#40;Mappings Page&#41;</span></span>](../flat-file-destination-editor-mappings-page.md)  
  
 <span data-ttu-id="64e22-124">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="64e22-124">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="64e22-125">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="64e22-125">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="64e22-126">Common Properties</span><span class="sxs-lookup"><span data-stu-id="64e22-126">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="64e22-127">Propiedades personalizadas de archivo plano</span><span class="sxs-lookup"><span data-stu-id="64e22-127">Flat File Custom Properties</span></span>](flat-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="64e22-128">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="64e22-128">Related Tasks</span></span>  
 <span data-ttu-id="64e22-129">Para obtener más detalles sobre cómo establecer las propiedades de un componente de flujo de datos, vea [Establecer las propiedades de un componente de flujo de datos](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="64e22-129">For information about how to set the properties of a data flow component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64e22-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64e22-130">See Also</span></span>  
 <span data-ttu-id="64e22-131">[Origen de archivo plano](flat-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="64e22-131">[Flat File Source](flat-file-source.md) </span></span>  
 [<span data-ttu-id="64e22-132">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="64e22-132">Data Flow</span></span>](data-flow.md)  
  
  
