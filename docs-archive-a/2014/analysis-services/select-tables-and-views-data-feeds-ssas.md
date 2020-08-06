---
title: Seleccionar tablas y vistas (fuentes de datos) (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.seltablesviewsdf.f1
ms.assetid: 6c4fafe0-e02e-47d1-b8bc-e70e872690af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 46c317ecf2a87adcde264e8d6d7e822eb833b8b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671715"
---
# <a name="select-tables-and-views-data-feeds-ssas"></a><span data-ttu-id="8d332-102">Seleccionar tablas y vistas (fuentes de distribución de datos) (SSAS)</span><span class="sxs-lookup"><span data-stu-id="8d332-102">Select Tables and Views (Data Feeds) (SSAS)</span></span>
  <span data-ttu-id="8d332-103">Esta página del **Asistente para la importación de tablas** le permite seleccionar las tablas y vistas de las que desea importar los datos.</span><span class="sxs-lookup"><span data-stu-id="8d332-103">This page of the **Table Import Wizard** enables you to select the tables and views that you want to import data from.</span></span> <span data-ttu-id="8d332-104">Para tener acceso al asistente desde [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el menú **Modelo** , haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="8d332-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="8d332-105">El hecho de que aparezcan tablas y vistas en esta página no garantiza que la importación se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="8d332-105">The appearance of tables and views on this page does not guarantee that import will succeed.</span></span> <span data-ttu-id="8d332-106">Si el usuario especificado en la página Información de suplantación no tiene privilegios suficientes para leer la base de datos seleccionada, la importación no se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="8d332-106">If the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
 <span data-ttu-id="8d332-107">Para los orígenes de datos que usan la autenticación de Windows, se utilizan las credenciales del usuario actual para capturar las tablas y vistas del cuadro de diálogo en Seleccionar tablas y vistas.</span><span class="sxs-lookup"><span data-stu-id="8d332-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the tables and views in the Select Tables and Views dialog.</span></span> <span data-ttu-id="8d332-108">Para capturar los datos de los demás orígenes de datos se usan las credenciales proporcionadas en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="8d332-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="8d332-109">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="8d332-109">UI element list</span></span>  
 <span data-ttu-id="8d332-110">**URL de fuente de distribución de datos**</span><span class="sxs-lookup"><span data-stu-id="8d332-110">**Data feed URL**</span></span>  
 <span data-ttu-id="8d332-111">Muestra la dirección URL para la fuente de distribución de datos que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="8d332-111">Displays the URL for the data feed that you selected.</span></span>  
  
 <span data-ttu-id="8d332-112">**Tablas y vistas**</span><span class="sxs-lookup"><span data-stu-id="8d332-112">**Tables and views**</span></span>  
 <span data-ttu-id="8d332-113">Enumera las tablas y vistas de la fuente de datos.</span><span class="sxs-lookup"><span data-stu-id="8d332-113">Lists the tables and views in the data feed.</span></span> <span data-ttu-id="8d332-114">Active la casilla situada al lado de cada tabla y vista que desee importar.</span><span class="sxs-lookup"><span data-stu-id="8d332-114">Select the checkbox beside each table and view that you want to import.</span></span>  
  
 <span data-ttu-id="8d332-115">**Tabla de origen**</span><span class="sxs-lookup"><span data-stu-id="8d332-115">**Source Table**</span></span>  
 <span data-ttu-id="8d332-116">Especifica el nombre de la tabla de origen basado en el tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8d332-116">Specifies the name of the source table based on the type of data source.</span></span>  
  
 <span data-ttu-id="8d332-117">**Nombre descriptivo**</span><span class="sxs-lookup"><span data-stu-id="8d332-117">**Friendly Name**</span></span>  
 <span data-ttu-id="8d332-118">Especifica el nombre descriptivo de la tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="8d332-118">Specifies the friendly name of the source table.</span></span> <span data-ttu-id="8d332-119">De forma predeterminada, la columna muestra el nombre de la tabla de origen que aparece en la columna **Tabla de origen** .</span><span class="sxs-lookup"><span data-stu-id="8d332-119">By default, the column displays the name of the source table that appears in the **Source Table** column.</span></span>  
  
 <span data-ttu-id="8d332-120">**Detalles del filtro**</span><span class="sxs-lookup"><span data-stu-id="8d332-120">**Filter Details**</span></span>  
 <span data-ttu-id="8d332-121">Muestra el filtro de importación de datos en el cuadro de diálogo **Detalles del filtro**, cuando se ha aplicado un filtro a los datos que se están importando.</span><span class="sxs-lookup"><span data-stu-id="8d332-121">Displays the data import filter in the **Filter Details** dialog box, when a filter has been applied to the data that is being imported.</span></span> <span data-ttu-id="8d332-122">Para obtener más información, vea [Detalles del filtro &#40;SSAS&#41;](filter-details-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="8d332-122">For more information, see [Filter Details &#40;SSAS&#41;](filter-details-ssas.md).</span></span>  
  
 <span data-ttu-id="8d332-123">**Vista previa y Filtro**</span><span class="sxs-lookup"><span data-stu-id="8d332-123">**Preview and Filter**</span></span>  
 <span data-ttu-id="8d332-124">Muestra el cuadro de diálogo **Vista previa de la tabla seleccionada** que se usa para aplicar un filtro a los datos que se están importando.</span><span class="sxs-lookup"><span data-stu-id="8d332-124">Displays the **Preview Selected Table** dialog box that is used to apply a filter to the data that is being imported.</span></span> <span data-ttu-id="8d332-125">Para obtener más información, consulte [Vista previa de la tabla seleccionada &#40;SSAS&#41;](preview-selected-table-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="8d332-125">For more information, see [Preview Selected Table &#40;SSAS&#41;](preview-selected-table-ssas.md).</span></span>  
  
 <span data-ttu-id="8d332-126">**Seleccionar tablas relacionadas**</span><span class="sxs-lookup"><span data-stu-id="8d332-126">**Select Related Tables**</span></span>  
 <span data-ttu-id="8d332-127">Seleccionar las tablas que se relacionan con las tablas y vistas que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8d332-127">Select tables that are related to the tables and views that you have selected.</span></span>  
  
  
