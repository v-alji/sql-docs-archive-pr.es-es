---
title: 'Opciones (editor de texto: Transact-SQL-IntelliSense) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.SQL.Advanced
- VS.ToolsOptionsPages.Text_Editor.SQL_Server_Tools.Advanced
dev_langs:
- TSQL
ms.assetid: 1855d916-5bf9-4d94-b0fb-9f9bb05ff950
author: rothja
ms.author: jroth
ms.openlocfilehash: 2d8f9c865516dc5e4c0ddadbdc908a9b4c8ec366
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674987"
---
# <a name="options-text-editor-transact-sql-intellisense"></a><span data-ttu-id="bebad-102">Opciones (editor de texto: Transact-SQL-IntelliSense)</span><span class="sxs-lookup"><span data-stu-id="bebad-102">Options (Text Editor-Transact-SQL-IntelliSense)</span></span>
  <span data-ttu-id="bebad-103">El cuadro de diálogo **Opciones** le permite modificar las opciones de IntelliSense para el Editor de consultas de [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bebad-103">The **Options** dialog box lets you change the IntelliSense settings for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor.</span></span> <span data-ttu-id="bebad-104">Estas opciones se encuentran disponibles cuando, en el menú **Herramientas**, se hace clic en **Opciones**, se expande la carpeta **Editor de texto**, se expande la carpeta **Transact-SQL** y se selecciona **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="bebad-104">These settings are available when, on the **Tools** menu, you click **Options**, expand the **Text Editor** folder, expand the **Transact-SQL** folder, and then click **Advanced**.</span></span>  
  
## <a name="transact-sql-intellisense-settings"></a><span data-ttu-id="bebad-105">Configuración de Transact-SQL IntelliSense</span><span class="sxs-lookup"><span data-stu-id="bebad-105">Transact-SQL IntelliSense Settings</span></span>  
 <span data-ttu-id="bebad-106">Especifica las opciones de IntelliSense para el Editor de consultas de [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bebad-106">Specifies the IntelliSense options for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor.</span></span>  
  
### <a name="enable-intellisense"></a><span data-ttu-id="bebad-107">Habilitar IntelliSense</span><span class="sxs-lookup"><span data-stu-id="bebad-107">Enable IntelliSense</span></span>  
 <span data-ttu-id="bebad-108">Habilita las características de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="bebad-108">Enables the IntelliSense features.</span></span> <span data-ttu-id="bebad-109">Si este cuadro no está seleccionado, las opciones específicas de IntelliSense no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="bebad-109">When this box is not selected, the specific IntelliSense options are unavailable.</span></span> <span data-ttu-id="bebad-110">De forma predeterminada, esta casilla está activada.</span><span class="sxs-lookup"><span data-stu-id="bebad-110">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="bebad-111">**Subrayar errores**</span><span class="sxs-lookup"><span data-stu-id="bebad-111">**Underline errors**</span></span>  
 <span data-ttu-id="bebad-112">Identifica errores sintácticos y semánticos en las instrucciones [!INCLUDE[tsql](../includes/tsql-md.md)] en la ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="bebad-112">Identifies syntax and semantic errors in [!INCLUDE[tsql](../includes/tsql-md.md)] statements in the query window.</span></span> <span data-ttu-id="bebad-113">Todos los errores y advertencias aparecen en rojo.</span><span class="sxs-lookup"><span data-stu-id="bebad-113">All errors and warnings appear in red.</span></span> <span data-ttu-id="bebad-114">Los errores y advertencias solo se admiten en las instrucciones [!INCLUDE[tsql](../includes/tsql-md.md)] para las que se ha implementado IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="bebad-114">Errors and warnings are supported only for the [!INCLUDE[tsql](../includes/tsql-md.md)] statements for which IntelliSense has been implemented.</span></span> <span data-ttu-id="bebad-115">De forma predeterminada, esta casilla está activada.</span><span class="sxs-lookup"><span data-stu-id="bebad-115">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="bebad-116">**Instrucciones de esquema**</span><span class="sxs-lookup"><span data-stu-id="bebad-116">**Outline statements**</span></span>  
 <span data-ttu-id="bebad-117">Habilita la función de esquematización al abrir un archivo.</span><span class="sxs-lookup"><span data-stu-id="bebad-117">Enables the outlining feature when a file is opened.</span></span> <span data-ttu-id="bebad-118">Esto crea bloques plegables de código [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bebad-118">This creates collapsible blocks of [!INCLUDE[tsql](../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="bebad-119">De forma predeterminada, esta casilla está activada.</span><span class="sxs-lookup"><span data-stu-id="bebad-119">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="bebad-120">**Tamaño máximo de script**</span><span class="sxs-lookup"><span data-stu-id="bebad-120">**Maximum script size**</span></span>  
 <span data-ttu-id="bebad-121">Especifica el tamaño en el que se deshabilita la funcionalidad de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="bebad-121">Specifies the size at which IntelliSense functionality is disabled.</span></span> <span data-ttu-id="bebad-122">Si un script supera el tamaño especificado, se emite un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="bebad-122">If a script exceeds the specified size, a warning message is issued.</span></span> <span data-ttu-id="bebad-123">Todas las características de IntelliSense, excepto la codificación en colores, se deshabilitan para esa ventana del editor.</span><span class="sxs-lookup"><span data-stu-id="bebad-123">All IntelliSense features, except color coding, are disabled for that editor window.</span></span> <span data-ttu-id="bebad-124">IntelliSense se vuelve a habilitar cuando se elimina el texto suficiente como para reducir el tamaño del script por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="bebad-124">IntelliSense is reenabled when enough text is deleted to reduce the script size to under the limit.</span></span> <span data-ttu-id="bebad-125">Si se habilita IntelliSense para los scripts grandes, se puede disminuir el rendimiento en equipos lentos.</span><span class="sxs-lookup"><span data-stu-id="bebad-125">Enabling IntelliSense for large script sizes can decrease performance on slow computers.</span></span> <span data-ttu-id="bebad-126">Los tamaños permitidos son 100 KB, 500 KB, 1 MB, 2 MB e Ilimitado.</span><span class="sxs-lookup"><span data-stu-id="bebad-126">The allowed sizes are 100 KB, 500 KB, 1 MB, 2 MB, and Unlimited.</span></span> <span data-ttu-id="bebad-127">El valor predeterminado es 1 MB.</span><span class="sxs-lookup"><span data-stu-id="bebad-127">The default is 1 MB.</span></span>  
  
 <span data-ttu-id="bebad-128">**Uso de mayúsculas o minúsculas en nombres de funciones integradas**</span><span class="sxs-lookup"><span data-stu-id="bebad-128">**Casing for built-in function names**</span></span>  
 <span data-ttu-id="bebad-129">Especifica si los nombres de funciones de [!INCLUDE[tsql](../includes/tsql-md.md)] integradas que están incluidas en listas de finalización usan letras mayúsculas, como DATEADD, o minúsculas, como dateadd.</span><span class="sxs-lookup"><span data-stu-id="bebad-129">Specifies whether the names of built-in [!INCLUDE[tsql](../includes/tsql-md.md)] functions that are included in completion lists use uppercase letters, such as DATEADD; or lowercase letters, such as dateadd.</span></span> <span data-ttu-id="bebad-130">Seleccione la opción que mejor convenga a las convenciones de codificación de [!INCLUDE[tsql](../includes/tsql-md.md)] que está utilizando.</span><span class="sxs-lookup"><span data-stu-id="bebad-130">Select the option that best matches the [!INCLUDE[tsql](../includes/tsql-md.md)] coding conventions that you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bebad-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bebad-131">See Also</span></span>  
 [<span data-ttu-id="bebad-132">Solución de problemas de IntelliSense &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="bebad-132">Troubleshooting IntelliSense &#40;SQL Server Management Studio&#41;</span></span>](../relational-databases/scripting/troubleshooting-intellisense.md)  
  
  
