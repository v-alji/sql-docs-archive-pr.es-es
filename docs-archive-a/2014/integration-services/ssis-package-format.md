---
title: Formato de paquete SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cfe0e5dc-5be3-4222-b721-fe83665edd94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 524c65ac5682b8efe8c4191697eb540f9acca82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745898"
---
# <a name="ssis-package-format"></a><span data-ttu-id="2c922-102">Formato de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="2c922-102">SSIS Package Format</span></span>
  <span data-ttu-id="2c922-103">En la versión actual de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], se han realizado cambios significativos en el formato de paquetes (archivo .dtsx) para que sea más fácil leer el formato y comparar paquetes.</span><span class="sxs-lookup"><span data-stu-id="2c922-103">In the current release of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], significant changes were made to the package format (.dtsx file) to make it easier to read the format and to compare packages.</span></span> <span data-ttu-id="2c922-104">También puede combinar de forma más confiable paquetes que no contienen cambios en conflicto o cambios almacenados en formato binario.</span><span class="sxs-lookup"><span data-stu-id="2c922-104">You can also more reliably merge packages that don't contain conflicting changes or changes stored in binary format.</span></span>  
  
 <span data-ttu-id="2c922-105">Para ver el formato de archivo de paquete DTSX actual, vea [ \[ MS-DTSX \] : especificaciones de formato de archivo XML de paquete de servicios de transformación de datos](https://go.microsoft.com/fwlink/?LinkId=233251).</span><span class="sxs-lookup"><span data-stu-id="2c922-105">To view the current DTSX package file format, see [\[MS-DTSX\]: Data Transformation Services Package XML File Format Specification](https://go.microsoft.com/fwlink/?LinkId=233251).</span></span>  
  
 <span data-ttu-id="2c922-106">En la lista siguiente se mencionan los cambios de formato de archivo.</span><span class="sxs-lookup"><span data-stu-id="2c922-106">The following list outlines the file format changes.</span></span> <span data-ttu-id="2c922-107">Para ver ejemplos de código de estos cambios, vea [Cambios de formato de paquetes en SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=233255)</span><span class="sxs-lookup"><span data-stu-id="2c922-107">To view code examples of these changes, see [Package Format Changes in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=233255).</span></span>  
  
-   <span data-ttu-id="2c922-108">Las convenciones de formato se han aplicado para que sea más fácil leer y comprender el archivo .dtsx.</span><span class="sxs-lookup"><span data-stu-id="2c922-108">Formatting conventions have been applied to make it easier to read and understand the .dtsx file.</span></span>  
  
-   <span data-ttu-id="2c922-109">El formato es más conciso.</span><span class="sxs-lookup"><span data-stu-id="2c922-109">The format is more concise.</span></span> <span data-ttu-id="2c922-110">Los elementos independientes de cada propiedad se han guardado como atributos, excepto PackageFormatVersion.</span><span class="sxs-lookup"><span data-stu-id="2c922-110">Separate elements for each property have been persisted as attributes, with the exception of the PackageFormatVersion.</span></span> <span data-ttu-id="2c922-111">Los atributos se muestran en orden alfabético y las propiedades que tienen valores predeterminados ya no se guardan.</span><span class="sxs-lookup"><span data-stu-id="2c922-111">Attributes are listed alphabetically, and properties that have default values are no longer persisted.</span></span> <span data-ttu-id="2c922-112">Finalmente, los elementos que pueden aparecer varias veces, ahora se encuentran dentro de un elemento primario.</span><span class="sxs-lookup"><span data-stu-id="2c922-112">Finally, elements that can appear multiple times, are now contained within a parent element.</span></span>  
  
-   <span data-ttu-id="2c922-113">La mayoría de los objetos dentro de un paquete al que se puede hacer referencia mediante otros objetos ahora tienen un atributo `refId` definido en el paquete XML.</span><span class="sxs-lookup"><span data-stu-id="2c922-113">Most objects within a package that can be referred to by other objects now have a `refId` attribute defined in the package XML.</span></span> <span data-ttu-id="2c922-114">En lugar los identificadores de linaje de almacenamiento, ahora se guarda `refID`.</span><span class="sxs-lookup"><span data-stu-id="2c922-114">Instead of persisting lineage IDs, the `refID` is now persisted.</span></span> <span data-ttu-id="2c922-115">Los identificadores de linaje todavía se utilizan en tiempo de ejecución y se vuelven a generar al cargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="2c922-115">Lineage IDs are still used within the runtime and regenerated when the package is loaded.</span></span>  
  
     <span data-ttu-id="2c922-116">El valor de `refId` es una cadena única que es legible y de fácil comprensión, comparará con GUID o los valores enteros.</span><span class="sxs-lookup"><span data-stu-id="2c922-116">The `refId` value is a unique string that is readable and understandable, compared to GUIDs or integer values.</span></span> <span data-ttu-id="2c922-117">La cadena es similar a los valores de ruta de acceso que se usan para las configuraciones de paquetes en versiones anteriores de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c922-117">The string is similar to path values used for package configurations in previous releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="2c922-118">Si se mezclan los cambios entre dos versiones de un paquete, `refId` se puede utilizar en operaciones de búsqueda y reemplazo para asegurarse de que todas las referencias al objeto se han actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c922-118">If you are merging changes between two versions of a package, the `refId` can be used in find/replace operations to ensure that all references to that object have been correctly updated.</span></span>  
  
-   <span data-ttu-id="2c922-119">La información de diseño se encuentra en una sección de CDATA.</span><span class="sxs-lookup"><span data-stu-id="2c922-119">The layout information is contained in a CData section.</span></span>  
  
-   <span data-ttu-id="2c922-120">Las anotaciones se conservan en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="2c922-120">Annotations are persisted in cleartext.</span></span> <span data-ttu-id="2c922-121">Esto hace más fácil extraer la información para la generación automatizada de documentación.</span><span class="sxs-lookup"><span data-stu-id="2c922-121">This makes it easier to extract the information for automated generation of documentation.</span></span>  
  
  
