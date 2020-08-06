---
title: 'Usar las anotaciones SQL: Identity y SQL: GUID | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:guid
- annotated XSD schemas, IDENTITY-type columns
- annotated XSD schemas, GUID values
- DiffGrams [SQLXML], annotations
- identity annotation
- XSD schemas [SQLXML], GUID values
- GUIDs [SQLXML]
- guid annotation
- sql:identity
- IDENTITY-type column
- XSD schemas [SQLXML], IDENTITY-type columns
- updategrams [SQLXML], GUID values
ms.assetid: 7661dfd0-6573-4692-a8f1-3597adcd33c4
author: rothja
ms.author: jroth
ms.openlocfilehash: dc5c08f158911edb0a1a0638fc4bcee1e05a248c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672899"
---
# <a name="using-the-sqlidentity-and-sqlguid-annotations"></a><span data-ttu-id="87fab-102">Utilizar las anotaciones sql:guid y sql:identity</span><span class="sxs-lookup"><span data-stu-id="87fab-102">Using the sql:identity and sql:guid Annotations</span></span>
  <span data-ttu-id="87fab-103">Puede especificar las `sql:identity` `sql:guid` anotaciones y en un esquema XSD en cualquier nodo que se asigne a una columna de base de datos en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="87fab-103">You can specify the `sql:identity` and `sql:guid` annotations in an XSD schema on any node that maps to a database column in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="87fab-104">Mientras que el formato de diagrama de actualización (updategram) admite los atributos `updg:at-identity` y `updg:guid`, el formato de DiffGram no.</span><span class="sxs-lookup"><span data-stu-id="87fab-104">Whereas the updategram format supports the `updg:at-identity` and `updg:guid` attributes, the DiffGram format does not.</span></span> <span data-ttu-id="87fab-105">El atributo `updg:at-identity` define el comportamiento al actualizar una columna de tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="87fab-105">The `updg:at-identity` attribute defines the behavior in updating an IDENTITY-type column.</span></span> <span data-ttu-id="87fab-106">El atributo `updg:guid` permite obtener un valor GUID de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y utilizarlo en el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="87fab-106">The `updg:guid` attribute allows you to obtain a GUID value from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and use it in the updategram.</span></span> <span data-ttu-id="87fab-107">Para obtener más información y ejemplos de trabajo, vea [Insertar datos mediante XML diagramas &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="87fab-107">For more information and working samples, see [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="87fab-108">Las anotaciones `sql:identity` y `sql:guid` extienden esta funcionalidad a los DiffGrams.</span><span class="sxs-lookup"><span data-stu-id="87fab-108">The `sql:identity` and `sql:guid` annotations extend this functionality to DiffGrams.</span></span>  
  
 <span data-ttu-id="87fab-109">Cuando se ejecuta un DiffGram, primero se convierte en un diagrama de actualización que después se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="87fab-109">When you execute a DiffGram, it is first converted to an updategram, and then the updategram is executed.</span></span> <span data-ttu-id="87fab-110">Al especificar las anotaciones `sql:identity` y `sql:guid` en el esquema XSD, lo que se está haciendo en realidad es definir el comportamiento de un diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="87fab-110">By specifying the `sql:identity` and `sql:guid` annotations in the XSD schema, you are in fact defining the behavior of an updategram.</span></span> <span data-ttu-id="87fab-111">Por consiguiente, todas las anotaciones se describen en el contexto de un diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="87fab-111">Therefore, all the annotations are described in the context of an updategram.</span></span> <span data-ttu-id="87fab-112">Las anotaciones se pueden utilizar tanto para DiffGrams como para diagramas de actualización; sin embargo, los diagramas de actualización ya proporcionan un modo más eficaz de administrar los valores de identidad y GUID.</span><span class="sxs-lookup"><span data-stu-id="87fab-112">The annotations can be used both for DiffGrams and updategrams; however, updategrams already provide a more powerful way of handling identity and GUID values.</span></span>  
  
 <span data-ttu-id="87fab-113">Las anotaciones `sql:identity` y `sql:guid` se pueden definir en un elemento de contenido complejo.</span><span class="sxs-lookup"><span data-stu-id="87fab-113">The `sql:identity` and `sql:guid` annotations can be defined on a complex content element.</span></span>  
  
## <a name="sqlidentity-annotation"></a><span data-ttu-id="87fab-114">Anotación sql:identity</span><span class="sxs-lookup"><span data-stu-id="87fab-114">sql:identity Annotation</span></span>  
 <span data-ttu-id="87fab-115">Puede especificar la anotación `sql:identity` en el esquema XSD en cualquier nodo que se asigne a una columna de base de datos de tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="87fab-115">You can specify the `sql:identity` annotation in the XSD schema on any node that maps to an IDENTITY-type database column.</span></span> <span data-ttu-id="87fab-116">El valor especificado para esta anotación define cómo se actualiza la columna de tipo de identidad (ya sea mediante el valor proporcionado en diagrama para modificar la columna o omitiendo el valor, en cuyo caso [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se usa un valor generado por para esta columna).</span><span class="sxs-lookup"><span data-stu-id="87fab-116">The value specified for this annotation defines how the IDENTITY-type column is updated (either by using the value provided in the updategram to modify the column or by ignoring the value, in which case a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-generated value is used for this column).</span></span>  
  
 <span data-ttu-id="87fab-117">A la anotación `sql:identity` se le pueden asignar dos valores:</span><span class="sxs-lookup"><span data-stu-id="87fab-117">The `sql:identity` annotation can be assigned two values:</span></span>  
  
 <span data-ttu-id="87fab-118">ignore</span><span class="sxs-lookup"><span data-stu-id="87fab-118">ignore</span></span>  
 <span data-ttu-id="87fab-119">Hace que el diagrama de actualización omita cualquier valor que se proporcione en el diagrama de actualización para esa columna y deje que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] genere el valor de identidad.</span><span class="sxs-lookup"><span data-stu-id="87fab-119">Directs the updategram to ignore any value that is provided in the updategram for that column and to rely on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to generate the identity value.</span></span>  
  
 <span data-ttu-id="87fab-120">useValue</span><span class="sxs-lookup"><span data-stu-id="87fab-120">useValue</span></span>  
 <span data-ttu-id="87fab-121">Hace que el diagrama de actualización utilice el valor que se proporciona en el diagrama de actualización para actualizar la columna de tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="87fab-121">Directs the updategram to use the value that is provided in the updategram to update the IDENTITY-type column.</span></span> <span data-ttu-id="87fab-122">Un diagrama de actualización no comprueba si la columna es un valor de identidad o no.</span><span class="sxs-lookup"><span data-stu-id="87fab-122">An updategram does not check whether the column is an identity value or not.</span></span>  
  
 <span data-ttu-id="87fab-123">Si el diagrama de actualización especifica un valor para la columna de tipo IDENTITY, se debe especificar `sql:identity="useValue"` en el esquema.</span><span class="sxs-lookup"><span data-stu-id="87fab-123">If the updategram specifies a value for the IDENTITY-type column, the `sql:identity="useValue"` must be specified in the schema.</span></span>  
  
## <a name="sqlguid-annotation"></a><span data-ttu-id="87fab-124">Anotación sql:guid</span><span class="sxs-lookup"><span data-stu-id="87fab-124">sql:guid Annotation</span></span>  
 <span data-ttu-id="87fab-125">Un diagrama de actualización puede hacer que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] genere un valor GUID para después utilizarlo en el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="87fab-125">An updategram can have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generate a GUID value and then use this value in the updategram.</span></span> <span data-ttu-id="87fab-126">En el contexto de los DiffGrams, puede utilizar la anotación `sql:guid` para especificar si desea utilizar un valor GUID generado por SQL Server o utilizar el valor que se proporciona en el diagrama de actualización para esa columna.</span><span class="sxs-lookup"><span data-stu-id="87fab-126">In the context of DiffGrams, you can use the `sql:guid` annotation to specify whether to use a GUID value that is generated by SQL Server or use the value that is provided in the updategram for that column.</span></span>  
  
 <span data-ttu-id="87fab-127">A la anotación `sql:guid` se le pueden asignar dos valores:</span><span class="sxs-lookup"><span data-stu-id="87fab-127">The `sql:guid` annotation can be assigned two values:</span></span>  
  
 <span data-ttu-id="87fab-128">generate</span><span class="sxs-lookup"><span data-stu-id="87fab-128">generate</span></span>  
 <span data-ttu-id="87fab-129">Especifica que el GUID generado por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se utilice para esa columna en la operación de actualización.</span><span class="sxs-lookup"><span data-stu-id="87fab-129">Specifies that the GUID generated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] be used for that column in the update operation.</span></span>  
  
 <span data-ttu-id="87fab-130">useValue</span><span class="sxs-lookup"><span data-stu-id="87fab-130">useValue</span></span>  
 <span data-ttu-id="87fab-131">Especifica que el valor especificado en el diagrama de actualización se utilice para la columna.</span><span class="sxs-lookup"><span data-stu-id="87fab-131">Specifies that the value specified in the updategram be used for the column.</span></span> <span data-ttu-id="87fab-132">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="87fab-132">This is the default value.</span></span>  
  
  
