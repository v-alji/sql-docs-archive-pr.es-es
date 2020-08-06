---
title: Modificar o eliminar una base de datos de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- databases [Analysis Services], modifying
- removing databases
- deleting databases
- dropping databases
- databases [Analysis Services], deleting
- modifying databases
ms.assetid: e48e3988-c091-4379-aabc-4da62f709a7e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6182e91bd95754fe639e8a48548b5cab1835bdc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749514"
---
# <a name="modify-or-delete-an-analysis-services-database"></a><span data-ttu-id="26df4-102">Modificar o eliminar una base de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="26df4-102">Modify or Delete an Analysis Services Database</span></span>
  <span data-ttu-id="26df4-103">Puede cambiar el nombre y la descripción de una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] antes de la implementación en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] y después de la implementación en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26df4-103">You can change the name and description of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database before deployment in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and after deployment in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="26df4-104">También puede ajustar parámetros adicionales de una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , de acuerdo al entorno.</span><span class="sxs-lookup"><span data-stu-id="26df4-104">You can also adjust additional settings on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, depending on the environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="26df4-105">No es posible cambiar las propiedades de una base de datos con [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] en modo en línea.</span><span class="sxs-lookup"><span data-stu-id="26df4-105">You cannot change database properties using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span>  
  
## <a name="modifying-databases-using-sql-server-management-studio"></a><span data-ttu-id="26df4-106">Modificar bases de datos mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="26df4-106">Modifying Databases Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="26df4-107">Una vez que se ha implementado una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , puede usar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para cambiar el modo de suplantación que utiliza [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cuando se conecta a los orígenes de datos que contiene la base de datos.</span><span class="sxs-lookup"><span data-stu-id="26df4-107">Once an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database is deployed, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to change the impersonation mode used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] when connecting to data sources contained by the database.</span></span> <span data-ttu-id="26df4-108">El modo de suplantación permite especificar el contexto de seguridad que usa [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cuando intenta conectarse a un origen de datos para el procesamiento, la exploración o la obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="26df4-108">The impersonation mode allows you to specify the security context used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] when attempting to connect to a data source for processing, browsing, or drillthrough purposes.</span></span>  
  
## <a name="modifying-databases-using-sql-server-data-tools"></a><span data-ttu-id="26df4-109">Modificar bases de datos mediante las Herramientas de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="26df4-109">Modifying Databases Using SQL Server Data Tools</span></span>  
 <span data-ttu-id="26df4-110">Puede utilizar [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] en modo de proyecto para modificar las traducciones del título y la descripción de un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que se usa para definir una base de datos.</span><span class="sxs-lookup"><span data-stu-id="26df4-110">You can use [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in project mode to modify the translations for the caption and description of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project used to define a database.</span></span> <span data-ttu-id="26df4-111">Para obtener más información sobre el uso de traducciones en una [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] base de datos, vea [escenarios de globalización para Analysis Services multidimensional](../globalization-scenarios-for-analysis-services-multiidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="26df4-111">For more information about using translations in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, see [Globalization scenarios for Analysis Services Multiidimensional](../globalization-scenarios-for-analysis-services-multiidimensional.md).</span></span>  
  
 <span data-ttu-id="26df4-112">También puede establecer los alias y las funciones de agregación asociados con los tipos de cuenta que utilizan los atributos de cuenta de las dimensiones incluidas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="26df4-112">You can also set the aliases and aggregation functions associated with account types used by account attributes in dimensions contained by the database.</span></span> <span data-ttu-id="26df4-113">Los alias permiten seleccionar la terminología empresarial específica que usa su organización para los tipos de cuenta de un plan de cuentas.</span><span class="sxs-lookup"><span data-stu-id="26df4-113">Aliases allow you to select the business-specific terminology used by your organization for the account types in a chart of accounts.</span></span> <span data-ttu-id="26df4-114">Los miembros de un atributo de cuenta utilizan los tipos de cuenta para indicar cómo se agregan medidas a cada miembro utilizando las funciones de agregación especificadas para cada tipo de cuenta que incluye la base de datos.</span><span class="sxs-lookup"><span data-stu-id="26df4-114">The account types are used by members of an account attribute to indicate how to aggregate measures over each member by using the aggregation functions specified for each account type contained in the database.</span></span> <span data-ttu-id="26df4-115">Para más información sobre los atributos de cuenta, vea [Atributos y jerarquías de atributos](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="26df4-115">For more information about account attributes, see [Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md).</span></span>  
  
## <a name="deleting-databases"></a><span data-ttu-id="26df4-116">eliminar bases de datos</span><span class="sxs-lookup"><span data-stu-id="26df4-116">Deleting Databases</span></span>  
 <span data-ttu-id="26df4-117">Al eliminar una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] existente, se eliminan todos los cubos, dimensiones y modelos de minería de datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="26df4-117">Deleting an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database deletes the database and all cubes, dimensions, and mining models in the database.</span></span> <span data-ttu-id="26df4-118">Solo puede eliminar una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] existente en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26df4-118">You can only delete an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-delete-an-analysis-services-database"></a><span data-ttu-id="26df4-119">Para eliminar una base de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="26df4-119">To delete an Analysis Services database</span></span>  
  
1.  <span data-ttu-id="26df4-120">Conéctese con una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26df4-120">Connect to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
2.  <span data-ttu-id="26df4-121">En el **Explorador de objetos**, expanda el nodo de la instancia conectada de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y asegúrese de que el objeto que va a eliminar está visible.</span><span class="sxs-lookup"><span data-stu-id="26df4-121">In **Object Explorer**, expand the node for the connected [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and ensure that the object to be deleted is visible.</span></span>  
  
3.  <span data-ttu-id="26df4-122">Haga clic con el botón derecho en el objeto que quiere eliminar y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="26df4-122">Right-click the object to be deleted and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="26df4-123">En el cuadro de diálogo **Eliminar objeto** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="26df4-123">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26df4-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26df4-124">See Also</span></span>  
 [<span data-ttu-id="26df4-125">Documentar y crear scripts en una base de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="26df4-125">Document and Script an Analysis Services Database</span></span>](document-and-script-an-analysis-services-database.md)  
  
  
