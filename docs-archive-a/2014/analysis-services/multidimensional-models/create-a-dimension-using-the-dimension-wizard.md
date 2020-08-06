---
title: Crear una dimensión mediante el Asistente para dimensiones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], creating
ms.assetid: d84f66ae-7551-49bf-99d0-88368ca2dd0e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9ec38dc7170b915dce0cedea60c93385560e11f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748348"
---
# <a name="create-a-dimension-using-the-dimension-wizard"></a><span data-ttu-id="dee10-102">Crear una dimensión usando el Asistente para dimensiones</span><span class="sxs-lookup"><span data-stu-id="dee10-102">Create a Dimension Using the Dimension Wizard</span></span>
  <span data-ttu-id="dee10-103">Crear una nueva dimensión usando el Asistente para dimensiones de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dee10-103">You can create a new dimension by using the Dimension Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-create-a-new-dimension"></a><span data-ttu-id="dee10-104">Para crear una nueva dimensión</span><span class="sxs-lookup"><span data-stu-id="dee10-104">To create a new dimension</span></span>  
  
1.  <span data-ttu-id="dee10-105">En **Explorador de soluciones**, haga clic con el botón secundario en **dimensiones**y, a continuación, haga clic en **nueva dimensión**.</span><span class="sxs-lookup"><span data-stu-id="dee10-105">In **Solution Explorer**, right-click **Dimensions**, and then click **New Dimension**.</span></span>  
  
2.  <span data-ttu-id="dee10-106">En la página **Seleccionar método de creación** del Asistente para dimensiones, seleccione **Usar una tabla existente**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dee10-106">On the **Select Creation Method** page of the Dimension Wizard, select **Use an existing table**, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dee10-107">Podría tener de vez en cuando que crear una dimensión sin utilizar una tabla existente.</span><span class="sxs-lookup"><span data-stu-id="dee10-107">You might occasionally have to create a dimension without using an existing table.</span></span> <span data-ttu-id="dee10-108">Para más información, vea [Crear una dimensión generando una tabla que no sea de tiempos en el origen de datos](create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md) y [Crear una dimensión de tiempo generando una tabla de tiempos](create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="dee10-108">For more information, see [Create a Dimension by Generating a Non-Time Table in the Data Source](create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md) and [Create a Time Dimension by Generating a Time Table](create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
3.  <span data-ttu-id="dee10-109">En la página **Especificar información de origen** , siga estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="dee10-109">On the **Specify Source Information** page, do the following procedures:</span></span>  
  
    1.  <span data-ttu-id="dee10-110">En la lista **Vista del origen de datos** , seleccione una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="dee10-110">In the **Data source view** list, select a data source view.</span></span>  
  
    2.  <span data-ttu-id="dee10-111">En la lista **Tabla principal** , seleccione la tabla de dimensiones principal.</span><span class="sxs-lookup"><span data-stu-id="dee10-111">In the **Main table** list, select the main dimension table.</span></span>  
  
    3.  <span data-ttu-id="dee10-112">En la lista **Columnas de clave** , revise las columnas de clave que ha seleccionado automáticamente el asistente en función de la clave principal definida en la tabla de dimensiones principal.</span><span class="sxs-lookup"><span data-stu-id="dee10-112">In the **Key columns** list, review the key columns that the wizard has automatically selected based on the primary key that is defined in the main dimension table.</span></span> <span data-ttu-id="dee10-113">Para cambiar esta configuración predeterminada, especifique las columnas de clave que vinculan la tabla de dimensiones a la tabla de hechos.</span><span class="sxs-lookup"><span data-stu-id="dee10-113">To change this default setting, specify the key columns that link the dimension table to the fact table.</span></span>  
  
    4.  <span data-ttu-id="dee10-114">En la lista desplegable **Columna de nombre** , revise la columna de nombre que ha seleccionado automáticamente el asistente.</span><span class="sxs-lookup"><span data-stu-id="dee10-114">In the **Name column** drop-down list, review the name column that the wizard has automatically selected.</span></span>  
  
         <span data-ttu-id="dee10-115">Este nombre predeterminado es adecuado cuando la columna contiene información descriptiva.</span><span class="sxs-lookup"><span data-stu-id="dee10-115">This default name is appropriate when the column contains descriptive information.</span></span> <span data-ttu-id="dee10-116">Sin embargo, podría desear especificar un nombre que contenga valores más significativos para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="dee10-116">However, you might want to specify a name that contains values that are more meaningful for the end user.</span></span> <span data-ttu-id="dee10-117">Por ejemplo, si un atributo de categoría de producto de una dimensión Products utiliza la columna **ProductCategoryKey** como su columna de clave, puede especificar la columna **ProductCategoryName** como su columna de nombre.</span><span class="sxs-lookup"><span data-stu-id="dee10-117">For example, if a product category attribute in a Products dimension uses the **ProductCategoryKey** column as its key column, you can specify the **ProductCategoryName** column as its name column.</span></span>  
  
         <span data-ttu-id="dee10-118">Si la lista **Columnas de clave** contiene varias columnas de clave, debe especificar una columna de nombre que proporcione los valores de miembro al atributo clave.</span><span class="sxs-lookup"><span data-stu-id="dee10-118">If the **Key columns** list contains multiple key columns, you must specify a name column that provides the member values for the key attribute.</span></span> <span data-ttu-id="dee10-119">Para ello, puede crear un cálculo con nombre en la vista de origen de datos y utilizarlo como columna de nombre.</span><span class="sxs-lookup"><span data-stu-id="dee10-119">To do this, you can create a named calculation in the data source view and use that as the name column.</span></span>  
  
    5.  <span data-ttu-id="dee10-120">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="dee10-120">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="dee10-121">En la página **Seleccionar tablas relacionadas** , seleccione las tablas relacionadas que desea incluir en su dimensión y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dee10-121">On the **Select Related Tables** page, select the related tables that you want to include in your dimension, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dee10-122"> La página **Seleccionar tablas relacionadas** aparece si la tabla de dimensiones principal que especificó tiene relaciones con otras tablas de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="dee10-122">The **Select Related Tables** page appears if the main dimension table that you specified has relationships to other dimension tables.</span></span>  
  
5.  <span data-ttu-id="dee10-123">En la página **Seleccionar los atributos de la dimensión** , seleccione los atributos que quiera incluir en la dimensión y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dee10-123">On the **Select Dimension Attributes** page, select the attributes that you want to include in the dimension, and then click **Next**.</span></span>  
  
     <span data-ttu-id="dee10-124">Opcionalmente, puede cambiar los nombres de los atributos, habilitar o deshabilitar la exploración y especificar el tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="dee10-124">Optionally, you can change the attribute names, enable or disable browsing, and specify the attribute type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dee10-125"> Para activar los campos **Habilitar exploración** y **Tipo de atributo** de un atributo, el atributo debe estar seleccionado para ser incluido en la dimensión.</span><span class="sxs-lookup"><span data-stu-id="dee10-125">To make the **Enable Browsing** and **Attribute Type** fields of an attribute active, the attribute must be selected for inclusion in the dimension.</span></span>  
  
6.  <span data-ttu-id="dee10-126">En la columna **Tipos de cuenta integrados** de la página **Definir la inteligencia de cuentas** , seleccione el tipo de cuenta y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dee10-126">On the **Define Account Intelligence** page, in the **Built-In Account Types** column, select the account type, and then click **Next**.</span></span>  
  
     <span data-ttu-id="dee10-127">El tipo de cuenta debe corresponder al tipo de cuenta de la tabla de origen que aparece en la columna **Tipos de cuenta de tabla de origen** .</span><span class="sxs-lookup"><span data-stu-id="dee10-127">The account type must correspond to the account type of the source table that is listed in the **Source Table Account Types** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dee10-128"> La página **Definir la inteligencia de cuentas** aparece si definió un atributo de dimensión **Tipo de cuenta** en la página **Seleccionar los atributos de la dimensión** del asistente.</span><span class="sxs-lookup"><span data-stu-id="dee10-128">The **Define Account Intelligence** page appears if you defined an **Account Type** dimension attribute on the **Select Dimension Attributes** page of the wizard.</span></span>  
  
7.  <span data-ttu-id="dee10-129">En la página **Finalización del asistente** , escriba un nombre para la nueva dimensión y revise la estructura de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="dee10-129">On the **Completing the Wizard** page, enter a name for the new dimension and review the dimension structure.</span></span> <span data-ttu-id="dee10-130">Si desea realizar modificaciones, haga clic **Atrás**; de lo contrario, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="dee10-130">If you want to make changes, click **Back**; otherwise, click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dee10-131">Puede utilizar el Diseñador de dimensiones una vez finalizado el Asistente para dimensiones para agregar, quitar o configurar atributos y jerarquías de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="dee10-131">You can use Dimension Designer after you complete the Dimension Wizard to add, remove, and configure attributes and hierarchies in the dimension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dee10-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dee10-132">See Also</span></span>  
 [<span data-ttu-id="dee10-133">Crear una dimensión usando una tabla existente</span><span class="sxs-lookup"><span data-stu-id="dee10-133">Create a Dimension by Using an Existing Table</span></span>](create-a-dimension-by-using-an-existing-table.md)  
  
  
