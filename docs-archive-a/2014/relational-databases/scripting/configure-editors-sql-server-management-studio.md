---
title: Configurar editores
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: e7c7a8ef-f561-4258-a7b6-c445dba69f87
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e94cdbcd310814081e146e3fd0dbe75260d1240
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746229"
---
# <a name="configure-editors-sql-server-management-studio"></a><span data-ttu-id="ac76a-102">Configurar editores (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ac76a-102">Configure Editors (SQL Server Management Studio)</span></span>
  <span data-ttu-id="ac76a-103">El funcionamiento de los editores de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] puede personalizarse configurando las opciones de cada editor.</span><span class="sxs-lookup"><span data-stu-id="ac76a-103">You can customize the operation of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] editors by configuring the options for each editor.</span></span>  
  
## <a name="settng-editor-options"></a><span data-ttu-id="ac76a-104">Configurar las opciones del editor</span><span class="sxs-lookup"><span data-stu-id="ac76a-104">Settng Editor Options</span></span>  
 <span data-ttu-id="ac76a-105">La mayoría de las opciones del editor se establecen a través del menú **Herramientas**, donde se selecciona **Opciones…** para mostrar un cuadro de diálogo **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="ac76a-105">Most of the editor options are set by using the **Tools** menu and selecting **Options...** to display an **Options** dialog.</span></span> <span data-ttu-id="ac76a-106">En el cuadro de diálogo **Opciones** , abra el nodo de **Editor de texto** en el panel izquierdo para configurar las opciones de edición de texto y código.</span><span class="sxs-lookup"><span data-stu-id="ac76a-106">In the **Options** dialog, open the **Text Editor** node in the left pane to set code and text editing options.</span></span> <span data-ttu-id="ac76a-107">Los nodos situados bajo Editor de texto se corresponden con editores concretos:</span><span class="sxs-lookup"><span data-stu-id="ac76a-107">The nodes under Text Editor apply to specific editors:</span></span>  
  
1.  <span data-ttu-id="ac76a-108">**Todos los lenguajes**: las opciones que se establecen a través de este nodo se aplican a todos los editores de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac76a-108">**All Languages** - options set using this node apply to all of the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] editors.</span></span> <span data-ttu-id="ac76a-109">Puede invalidar estos valores estableciendo opciones distintas para un editor concreto en los demás nodos.</span><span class="sxs-lookup"><span data-stu-id="ac76a-109">You can override these settings by using the other nodes to set different options for a specific editor.</span></span>  
  
2.  <span data-ttu-id="ac76a-110">**Texto sin formato**: las opciones que se establecen a través de este nodo se aplican a editores MDX, DMX y de texto.</span><span class="sxs-lookup"><span data-stu-id="ac76a-110">**Plain Text** - options set using this node apply to the MDX, DMX, and text editors.</span></span>  
  
3.  <span data-ttu-id="ac76a-111">**Transact-SQL**: las opciones que se establecen a través de este nodo se aplican al editor de consultas del motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="ac76a-111">**Transact-SQL** - options set using this node apply to the Database Engine Query Editor.</span></span>  
  
4.  <span data-ttu-id="ac76a-112">**XML**: las opciones que se establecen a través de este nodo se aplican al editor de XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="ac76a-112">**XML** - options set using this node apply to the XML for Analysis editor.</span></span>  
  
 <span data-ttu-id="ac76a-113">Abra los nodos **Ejecución de la consulta** o **Resultados de la consulta** para personalizar la ejecución de consultas y el modo en que se muestran los resultados.</span><span class="sxs-lookup"><span data-stu-id="ac76a-113">Open the **Query Execution** or **Query Results** nodes to customize the execution of queries and how the results are displayed.</span></span>  
  
## <a name="editor-configuration-tasks"></a><span data-ttu-id="ac76a-114">Tareas de configuración del editor</span><span class="sxs-lookup"><span data-stu-id="ac76a-114">Editor Configuration Tasks</span></span>  
  
|<span data-ttu-id="ac76a-115">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="ac76a-115">Task Description</span></span>|<span data-ttu-id="ac76a-116">Tema</span><span class="sxs-lookup"><span data-stu-id="ac76a-116">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="ac76a-117">Describe cómo se especifica que un editor debe abrirse haciendo doble clic en un archivo con la extensión especificada en el Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="ac76a-117">Describes how to specify that an editor be opened by double-clicking on a file with a specified extension in Windows Explorer.</span></span>|[<span data-ttu-id="ac76a-118">Asociar extensiones de archivo a un editor de código</span><span class="sxs-lookup"><span data-stu-id="ac76a-118">Associate File Extensions to a Code Editor</span></span>](associate-file-extensions-to-a-code-editor.md)|  
|<span data-ttu-id="ac76a-119">Describe cómo se personalizan las fuentes para mejorar la legibilidad del código y del texto.</span><span class="sxs-lookup"><span data-stu-id="ac76a-119">Describes how to customize fonts to make code and text more readable.</span></span>|[<span data-ttu-id="ac76a-120">Cambiar el color, el tamaño y el estilo de la fuente</span><span class="sxs-lookup"><span data-stu-id="ac76a-120">Change Font Color, Size, and Style</span></span>](change-font-color-size-and-style.md)|  
|<span data-ttu-id="ac76a-121">Describe cómo se consultan las propiedades.</span><span class="sxs-lookup"><span data-stu-id="ac76a-121">Describes how to view properties.</span></span>|[<span data-ttu-id="ac76a-122">Usar la ventana Propiedades en Management Studio</span><span class="sxs-lookup"><span data-stu-id="ac76a-122">Use the Properties Window in Management Studio</span></span>](use-the-properties-window-in-management-studio.md)|  
|<span data-ttu-id="ac76a-123">Ubicación de las páginas de Ayuda F1 de los cuadros de diálogo de opciones de editores.</span><span class="sxs-lookup"><span data-stu-id="ac76a-123">Location of the F1 help pages for the editor options dialogs.</span></span>|[<span data-ttu-id="ac76a-124">Páginas de Opciones de consulta (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="ac76a-124">Query Options Pages F1 Help</span></span>](../../database-engine/query-options-pages-f1-help.md)|  
  
  
