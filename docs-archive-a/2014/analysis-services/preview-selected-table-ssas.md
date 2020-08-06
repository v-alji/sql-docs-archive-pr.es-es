---
title: Vista previa de la tabla seleccionada (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.previewselecttable.f1
ms.assetid: b6b34b5a-43b3-4a75-9f3b-b2ad1084b1b6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25eb4d4424223449052ab1f65b41cf270da81fb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750274"
---
# <a name="preview-selected-table-ssas"></a><span data-ttu-id="20a9a-102">Vista previa de la tabla seleccionada (SSAS)</span><span class="sxs-lookup"><span data-stu-id="20a9a-102">Preview Selected Table (SSAS)</span></span>
  <span data-ttu-id="20a9a-103">Esta página del **Asistente para la importación de tablas** le permite obtener una vista previa de los datos de la tabla seleccionada, seleccionar las columnas que se van a incluir en la importación de datos y filtrar los datos de las columnas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="20a9a-103">This page of the **Table Import Wizard** enables you to preview the data in the selected table, to select the columns to include in the data import, and to filter data in the selected columns.</span></span> <span data-ttu-id="20a9a-104">Para tener acceso al asistente desde [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el menú **Modelo** , haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="20a9a-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="20a9a-105">No se muestran todas las filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="20a9a-105">Not all the rows in the table are displayed.</span></span> <span data-ttu-id="20a9a-106">Sin embargo, los filtros que establezca se aplicarán a todos los datos de la tabla durante la importación.</span><span class="sxs-lookup"><span data-stu-id="20a9a-106">However, the filters that you set will be applied to all of the data in the table during import.</span></span>  
  
 <span data-ttu-id="20a9a-107">Para los orígenes de datos que usan la autenticación de Windows, se utilizan las credenciales del usuario actual para capturar los datos mostrados en el cuadro de diálogo Vista previa y aplicar filtro.</span><span class="sxs-lookup"><span data-stu-id="20a9a-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the data displayed in the Preview and Filter dialog.</span></span> <span data-ttu-id="20a9a-108">Para capturar los datos de los demás orígenes de datos se usan las credenciales proporcionadas en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="20a9a-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
 <span data-ttu-id="20a9a-109">El hecho de que aparezcan datos en esta página no garantiza que la importación se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="20a9a-109">The appearance of data on this page does not guarantee import will succeed.</span></span> <span data-ttu-id="20a9a-110">Si el nombre de usuario especificado en la página Información de suplantación no tiene privilegios suficientes para leer la base de datos seleccionada, la importación no se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="20a9a-110">If the user name specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="20a9a-111">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="20a9a-111">UI element list</span></span>  
 <span data-ttu-id="20a9a-112">**Casilla en el encabezado de columna**</span><span class="sxs-lookup"><span data-stu-id="20a9a-112">**Checkbox in the column header**</span></span>  
 <span data-ttu-id="20a9a-113">Active la casilla para incluir la columna en la importación de datos.</span><span class="sxs-lookup"><span data-stu-id="20a9a-113">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="20a9a-114">Desactive la casilla para quitar la columna de la importación de datos.</span><span class="sxs-lookup"><span data-stu-id="20a9a-114">Clear the checkbox to remove the column from the data import.</span></span>  
  
 <span data-ttu-id="20a9a-115">**Botón de flecha abajo en el encabezado de columna**</span><span class="sxs-lookup"><span data-stu-id="20a9a-115">**Down-arrow button in the column header**</span></span>  
 <span data-ttu-id="20a9a-116">Filtre los datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="20a9a-116">Filter data in the column.</span></span>  
  
 <span data-ttu-id="20a9a-117">**Borrar filtros de fila**</span><span class="sxs-lookup"><span data-stu-id="20a9a-117">**Clear Row Filters**</span></span>  
 <span data-ttu-id="20a9a-118">Quite todos los filtros que se aplicaron a los datos en las columnas.</span><span class="sxs-lookup"><span data-stu-id="20a9a-118">Remove all filters that were applied to the data in the columns.</span></span>  
  
  
