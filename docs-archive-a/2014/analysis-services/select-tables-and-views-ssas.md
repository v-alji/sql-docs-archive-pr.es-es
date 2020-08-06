---
title: Seleccionar tablas y vistas (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.seltablesviews.f1
ms.assetid: 5e8121cc-03f0-4168-98cf-63c5c032bb0b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 891da51478670122f5dbce8fdd7be55c98c898c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748959"
---
# <a name="select-tables-and-views-ssas"></a><span data-ttu-id="89e5b-102">Seleccionar tablas y vistas (SSAS)</span><span class="sxs-lookup"><span data-stu-id="89e5b-102">Select Tables and Views (SSAS)</span></span>
  <span data-ttu-id="89e5b-103">Esta página del **Asistente para la importación de tablas** le permite seleccionar las tablas y vistas de las que desea importar los datos.</span><span class="sxs-lookup"><span data-stu-id="89e5b-103">This page of the **Table Import Wizard** enables you to select the tables and views that you want to import data from.</span></span> <span data-ttu-id="89e5b-104">Para tener acceso al asistente desde [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el menú **Modelo** , haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="89e5b-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="89e5b-105">El hecho de que aparezcan tablas y vistas en esta página no garantiza que la importación se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="89e5b-105">The appearance of tables and views on this page does not guarantee that import will succeed.</span></span> <span data-ttu-id="89e5b-106">Si el usuario especificado en la página Información de suplantación no tiene privilegios suficientes para leer la base de datos seleccionada, la importación no se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="89e5b-106">If the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
 <span data-ttu-id="89e5b-107">Para los orígenes de datos que usan la autenticación de Windows, se utilizan las credenciales del usuario actual para capturar las tablas y vistas del cuadro de diálogo en Seleccionar tablas y vistas.</span><span class="sxs-lookup"><span data-stu-id="89e5b-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the tables and views in the Select Tables and Views dialog.</span></span> <span data-ttu-id="89e5b-108">Para capturar los datos de los demás orígenes de datos se usan las credenciales proporcionadas en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="89e5b-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="89e5b-109">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="89e5b-109">UI element list</span></span>  
 <span data-ttu-id="89e5b-110">**Server**</span><span class="sxs-lookup"><span data-stu-id="89e5b-110">**Server**</span></span>  
 <span data-ttu-id="89e5b-111">Muestra el servidor con que está conectado.</span><span class="sxs-lookup"><span data-stu-id="89e5b-111">Displays the server that you are connected to.</span></span>  
  
 <span data-ttu-id="89e5b-112">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="89e5b-112">**Database**</span></span>  
 <span data-ttu-id="89e5b-113">Muestra la base de datos que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="89e5b-113">Displays the database that you selected.</span></span>  
  
 <span data-ttu-id="89e5b-114">**Tablas y vistas**</span><span class="sxs-lookup"><span data-stu-id="89e5b-114">**Tables and Views**</span></span>  
 <span data-ttu-id="89e5b-115">Enumera las tablas y vistas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="89e5b-115">Lists the tables and views in the database.</span></span> <span data-ttu-id="89e5b-116">Active la casilla situada al lado de cada tabla y vista que desee importar.</span><span class="sxs-lookup"><span data-stu-id="89e5b-116">Select the checkbox beside each table and view that you want to import.</span></span>  
  
 <span data-ttu-id="89e5b-117">**Tabla de origen**</span><span class="sxs-lookup"><span data-stu-id="89e5b-117">**Source Table**</span></span>  
 <span data-ttu-id="89e5b-118">Especifica el nombre de la tabla de origen basado en el tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="89e5b-118">Specifies the name of the source table based on the type of data source.</span></span>  
  
 <span data-ttu-id="89e5b-119">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="89e5b-119">**Schema**</span></span>  
 <span data-ttu-id="89e5b-120">Especifica el esquema en el que está la tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="89e5b-120">Specifies the schema in which the source table is contained.</span></span> <span data-ttu-id="89e5b-121">En función del tipo de base de datos, un esquema funciona como un contenedor para otros objetos, como tablas, y también puede indicar la propiedad de esos objetos.</span><span class="sxs-lookup"><span data-stu-id="89e5b-121">Depending on the type of database, a schema functions as a container for other objects, such as tables, and can also indicate ownership of those objects.</span></span>  
  
 <span data-ttu-id="89e5b-122">**Nombre descriptivo**</span><span class="sxs-lookup"><span data-stu-id="89e5b-122">**Friendly Name**</span></span>  
 <span data-ttu-id="89e5b-123">Especifica el nombre descriptivo de la tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="89e5b-123">Specifies the friendly name of the source table.</span></span> <span data-ttu-id="89e5b-124">De forma predeterminada, la columna muestra el nombre de la tabla de origen que aparece en la columna **Tabla de origen** .</span><span class="sxs-lookup"><span data-stu-id="89e5b-124">By default, the column displays the name of the source table that appears in the **Source Table** column.</span></span> <span data-ttu-id="89e5b-125">Cambie el nombre si desea utilizar un nombre distinto del que se usa en la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="89e5b-125">Change the name if you want to use a different name than the name used in the source database.</span></span>  
  
 <span data-ttu-id="89e5b-126">**Detalles del filtro**</span><span class="sxs-lookup"><span data-stu-id="89e5b-126">**Filter Details**</span></span>  
 <span data-ttu-id="89e5b-127">Cuando se ha aplicado un filtro a los datos que se están importando, muestra el filtro de importación de datos en el cuadro de diálogo **Detalles del filtro**.</span><span class="sxs-lookup"><span data-stu-id="89e5b-127">When a filter has been applied to the data that is being imported, displays the data import filter in the **Filter Details** dialog box.</span></span> <span data-ttu-id="89e5b-128">Para obtener más información, vea [Detalles del filtro &#40;SSAS&#41;](filter-details-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="89e5b-128">For more information, see [Filter Details &#40;SSAS&#41;](filter-details-ssas.md).</span></span>  
  
 <span data-ttu-id="89e5b-129">**Vista previa y Filtro**</span><span class="sxs-lookup"><span data-stu-id="89e5b-129">**Preview and Filter**</span></span>  
 <span data-ttu-id="89e5b-130">Muestra el cuadro de diálogo **Vista previa de la tabla seleccionada** que se usa para aplicar un filtro a los datos que se están importando.</span><span class="sxs-lookup"><span data-stu-id="89e5b-130">Displays the **Preview Selected Table** dialog box that is used to apply a filter to the data that is being imported.</span></span> <span data-ttu-id="89e5b-131">Para obtener más información, consulte [Vista previa de la tabla seleccionada &#40;SSAS&#41;](preview-selected-table-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="89e5b-131">For more information, see [Preview Selected Table &#40;SSAS&#41;](preview-selected-table-ssas.md).</span></span>  
  
 <span data-ttu-id="89e5b-132">**Seleccionar tablas relacionadas**</span><span class="sxs-lookup"><span data-stu-id="89e5b-132">**Select Related Tables**</span></span>  
 <span data-ttu-id="89e5b-133">Se importan las tablas y vistas que se relacionan con las tablas y vistas que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="89e5b-133">Selects for import those tables and views that are related to the tables and views that you have already selected.</span></span>  
  
  
