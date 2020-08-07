---
title: Crear una cuenta financiera de una dimensión de tipo primario-secundario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], account
- account dimensions [Analysis Services]
- adding account intelligence
- account intelligence [Analysis Services]
ms.assetid: 2ba74e81-5b4b-407e-acdf-deb2f6accf0a
author: minewiskan
ms.author: owend
ms.openlocfilehash: ba10e642425628426d9183be2b8d2c4ff751c3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745458"
---
# <a name="create-a-finance-account-of-parent-child-type-dimension"></a><span data-ttu-id="3d662-102">Crear una cuenta financiera de una dimensión de tipo primario-secundario</span><span class="sxs-lookup"><span data-stu-id="3d662-102">Create a Finance Account of parent-child type Dimension</span></span>
  <span data-ttu-id="3d662-103">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , una dimensión de tipo cuenta es una dimensión cuyos atributos representan un gráfico de cuentas para la elaboración de informes financieros.</span><span class="sxs-lookup"><span data-stu-id="3d662-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], an account type dimension is a dimension whose attributes represent a chart of accounts for financial reporting purposes.</span></span>  
  
 <span data-ttu-id="3d662-104">Una dimensión de cuenta le permite administrar de forma selectiva el comportamiento de las agregaciones dentro de las cuentas a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="3d662-104">An account dimension lets you selectively manage aggregation behavior across accounts over time.</span></span> <span data-ttu-id="3d662-105">Una dimensión de cuenta también permite utilizar un mecanismo estándar para resolver la mayoría de los problemas de agregación no estándar que suelen detectarse en las soluciones de Business Intelligence que procesan datos financieros.</span><span class="sxs-lookup"><span data-stu-id="3d662-105">An account dimension also lets use a standard mechanism to resolve most of the nonstandard aggregation issues typically encountered in business intelligence solutions that handle financial data.</span></span> <span data-ttu-id="3d662-106">Si no se dispone de un mecanismo estándar parecido, para solucionar los problemas de agregación no estándar se necesitan fórmulas de resumen personalizadas, miembros calculados o scripts MDX (Expresiones multidimensionales).</span><span class="sxs-lookup"><span data-stu-id="3d662-106">If you did not have such a standard mechanism, resolving these nonstandard aggregation issues would require custom rollup formulas, calculated members, or Multidimensional Expressions (MDX) scripts.</span></span>  
  
 <span data-ttu-id="3d662-107">Para identificar una dimensión como una dimensión de cuenta, establezca la propiedad `Type` de la dimensión en `Accounts`.</span><span class="sxs-lookup"><span data-stu-id="3d662-107">To identify a dimension as an account dimension, set the `Type` property of the dimension to `Accounts`.</span></span>  
  
## <a name="dimension-structure"></a><span data-ttu-id="3d662-108">Estructura de dimensión</span><span class="sxs-lookup"><span data-stu-id="3d662-108">Dimension Structure</span></span>  
 <span data-ttu-id="3d662-109">Una dimensión de cuenta contiene, como mínimo, dos atributos:</span><span class="sxs-lookup"><span data-stu-id="3d662-109">An account dimension contains, at least, two attributes:</span></span>  
  
-   <span data-ttu-id="3d662-110">Un atributo clave: atributo que identifica las cuentas individuales de la tabla de dimensiones para la dimensión de cuenta.</span><span class="sxs-lookup"><span data-stu-id="3d662-110">A key attribute-an attribute that identifies individual accounts in the dimension table for the account dimension.</span></span>  
  
-   <span data-ttu-id="3d662-111">Un atributo de cuenta: un atributo primario que describe el modo en que las cuentas se organizan jerárquicamente en la dimensión de cuenta.</span><span class="sxs-lookup"><span data-stu-id="3d662-111">An account attribute-a parent attribute that describes how accounts are hierarchically arranged in the account dimension.</span></span>  
  
     <span data-ttu-id="3d662-112">Para identificar un atributo como un atributo de cuenta, establezca la propiedad `Type` del atributo en `Account` y la propiedad `Usage` en `Parent`.</span><span class="sxs-lookup"><span data-stu-id="3d662-112">To identify an attribute as an account attribute, set the `Type` property of the attribute to `Account` and the `Usage` property to `Parent`.</span></span>  
  
 <span data-ttu-id="3d662-113">Las dimensiones de cuenta pueden opcionalmente contener los siguientes atributos:</span><span class="sxs-lookup"><span data-stu-id="3d662-113">Account dimensions can optionally contain the following attributes:</span></span>  
  
-   <span data-ttu-id="3d662-114">Un atributo de tipo de cuenta: un atributo que define el tipo de cuenta de cada cuenta de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="3d662-114">An account type attribute-an attribute that defines the account type for each account in the dimension.</span></span> <span data-ttu-id="3d662-115">Los nombres de miembros del atributo de tipo de cuenta se asignan a los tipos de cuenta definidos para la base de datos o proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e indican la función de agregación utilizada por [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para esas cuentas.</span><span class="sxs-lookup"><span data-stu-id="3d662-115">The member names of the account type attribute map to the account types defined for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or project, and indicate the aggregation function used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for those accounts.</span></span> <span data-ttu-id="3d662-116">También pueden utilizarse operadores unarios o fórmulas de resumen personalizadas para determinar el comportamiento de la agregación para los atributos de cuenta, pero los tipos de cuenta permiten aplicar con más facilidad un comportamiento coherente a un gráfico de cuentas sin necesidad de realizar cambios en la base de datos relacional subyacente.</span><span class="sxs-lookup"><span data-stu-id="3d662-116">You can also use unary operators or custom rollup formulas to determine aggregation behavior for account attributes, but account types let you to easily apply consistent behavior to a chart of accounts without requiring changes to the underlying relational database.</span></span>  
  
     <span data-ttu-id="3d662-117">Para identificar un atributo de tipo de cuenta, establezca la propiedad `Type` del atributo en `AccountType`.</span><span class="sxs-lookup"><span data-stu-id="3d662-117">To identify an account type attribute, set the `Type` property of the attribute to `AccountType`.</span></span>  
  
-   <span data-ttu-id="3d662-118">Un atributo de nombre de cuenta: atributo que se utiliza para la elaboración de informes.</span><span class="sxs-lookup"><span data-stu-id="3d662-118">An account name attribute-an attribute that is used for reporting purposes.</span></span> <span data-ttu-id="3d662-119">Para identificar un atributo de nombre de cuenta, establezca la propiedad `Type` del atributo en `AccountName`.</span><span class="sxs-lookup"><span data-stu-id="3d662-119">You identify an account name attribute by setting the `Type` property of the attribute to `AccountName`.</span></span>  
  
-   <span data-ttu-id="3d662-120">Un atributo de número de cuenta: atributo que se utiliza para la elaboración de informes.</span><span class="sxs-lookup"><span data-stu-id="3d662-120">An account number attribute-an attribute that is used for reporting purposes.</span></span> <span data-ttu-id="3d662-121">Para identificar un atributo de número de cuenta, establezca la propiedad `Type` del atributo en `AccountNumber`.</span><span class="sxs-lookup"><span data-stu-id="3d662-121">You identify an account number attribute by setting the `Type` property of the attribute to `AccountNumber`.</span></span>  
  
 <span data-ttu-id="3d662-122">Para obtener más información sobre tipos de atributo, vea [Configurar tipos de atributos](attribute-properties-configure-attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="3d662-122">For more information about attribute types, see [Configure Attribute Types](attribute-properties-configure-attribute-types.md).</span></span>  
  
## <a name="adding-account-intelligence-with-the-business-intelligence-wizard"></a><span data-ttu-id="3d662-123">Agregar inteligencia de cuentas mediante el Asistente de Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="3d662-123">Adding Account Intelligence with the Business Intelligence Wizard</span></span>  
 <span data-ttu-id="3d662-124">Tras haber definido una dimensión de cuenta y haber agregado dicha dimensión a un cubo, puede utilizar el Asistente de Business Intelligence para agregar la funcionalidad de inteligencia de cuentas, como, por ejemplo, la asignación de tipos de cuenta, a la dimensión.</span><span class="sxs-lookup"><span data-stu-id="3d662-124">After you have defined an account dimension and added that dimension to a cube, you can use the Business Intelligence Wizard to adding account intelligence functionality, such as identifying and mapping account types, to the dimension.</span></span> <span data-ttu-id="3d662-125">Para obtener más información, vea [Agregar inteligencia de cuentas a una dimensión](bi-wizard-add-account-intelligence-to-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="3d662-125">For more information, see [Add Account Intelligence to a Dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d662-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3d662-126">See Also</span></span>  
 <span data-ttu-id="3d662-127">[Atributos y jerarquías de atributos](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="3d662-127">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="3d662-128">[Asistente de Business Intelligence (ayuda F1)](../business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="3d662-128">[Business Intelligence Wizard F1 Help](../business-intelligence-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="3d662-129">Tipos de dimensiones</span><span class="sxs-lookup"><span data-stu-id="3d662-129">Dimension Types</span></span>](../multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
