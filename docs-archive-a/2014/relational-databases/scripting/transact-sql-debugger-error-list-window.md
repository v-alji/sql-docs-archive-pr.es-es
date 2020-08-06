---
title: Ventana de lista de errores
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- error list window
- SQL Server Management Studio [SQL Server], error list window
ms.assetid: fae6327d-e268-44ae-a474-4a8f8f843129
author: rothja
ms.author: jroth
ms.openlocfilehash: 00455c339344b7b38a48500c49d139aa52df6116
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677000"
---
# <a name="error-list-window-management-studio"></a><span data-ttu-id="c04ca-102">Ventana Lista de errores (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c04ca-102">Error List Window (Management Studio)</span></span>
  <span data-ttu-id="c04ca-103">La ventana [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Lista de errores**de** muestra los errores sintácticos y semánticos generados a partir del código de IntelliSense en el Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c04ca-103">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Error List** displays the syntax and semantic errors that are generated from the IntelliSense code in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
## <a name="features-of-the-error-list"></a><span data-ttu-id="c04ca-104">Características de la ventana Lista de errores</span><span class="sxs-lookup"><span data-stu-id="c04ca-104">Features of the Error List</span></span>  
 <span data-ttu-id="c04ca-105">La ventana **Lista de errores** proporciona la funcionalidad siguiente:</span><span class="sxs-lookup"><span data-stu-id="c04ca-105">The **Error List** provides the following functionality:</span></span>  
  
-   <span data-ttu-id="c04ca-106">A medida que se modifican los scripts, la **Lista de errores** muestra las advertencias y los errores generados por IntelliSense en el Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c04ca-106">As you edit scripts, the **Error List** displays the errors and warnings produced by IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
-   <span data-ttu-id="c04ca-107">Puede hacer doble clic en la entrada de cualquier mensaje de error para situarse en la pestaña del archivo de script que generó el error y desplazarse a la ubicación de éste.</span><span class="sxs-lookup"><span data-stu-id="c04ca-107">You can double-click any error message entry to focus on the tab for the script file that generated the error, and move to the error location.</span></span>  
  
-   <span data-ttu-id="c04ca-108">Puede filtrar las entradas que desea mostrar, así como las columnas de información que desea que aparezcan para cada entrada.</span><span class="sxs-lookup"><span data-stu-id="c04ca-108">You can filter which entries you want to display, and which columns of information you want appear for each entry.</span></span>  
  
-   <span data-ttu-id="c04ca-109">Después de corregir un error, la entrada de error se elimina de la ventana **Lista de errores**.</span><span class="sxs-lookup"><span data-stu-id="c04ca-109">After you fix an error, the error entry is removed from the **Error List**.</span></span>  
  
-   <span data-ttu-id="c04ca-110">Al cerrar la pestaña para un archivo de script de [!INCLUDE[tsql](../../includes/tsql-md.md)] , los errores generados en ese archivo se eliminan de la ventana **Lista de errores**.</span><span class="sxs-lookup"><span data-stu-id="c04ca-110">When you close the tab for a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file, the errors for that file are removed from the **Error List**.</span></span>  
  
## <a name="working-with-the-error-list"></a><span data-ttu-id="c04ca-111">Trabajar con la ventana Lista de errores</span><span class="sxs-lookup"><span data-stu-id="c04ca-111">Working with the Error List</span></span>  
 <span data-ttu-id="c04ca-112">Para mostrar la ventana **Lista de errores**, realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="c04ca-112">To display the **Error List**, do one of the following:</span></span>  
  
-   <span data-ttu-id="c04ca-113">En el menú **Ver** , haga clic en **Lista de errores**.</span><span class="sxs-lookup"><span data-stu-id="c04ca-113">On the **View** menu, click **Error List**.</span></span>  
  
-   <span data-ttu-id="c04ca-114">Use el método abreviado de teclado CTRL+\\, CTRL+E.</span><span class="sxs-lookup"><span data-stu-id="c04ca-114">Enter the keyboard shortcut CTRL+\\, CTRL+E.</span></span>  
  
 <span data-ttu-id="c04ca-115">Después de abrir la ventana **Lista de errores**, puede personalizar la vista mediante las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c04ca-115">After you open the **Error List**, you can customize your view by performing the following actions:</span></span>  
  
-   <span data-ttu-id="c04ca-116">Para ordenar la lista, haga clic en cualquier encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="c04ca-116">To sort the list, click any column header.</span></span> <span data-ttu-id="c04ca-117">Para ordenar de nuevo por una columna adicional, presione y mantenga presionada la tecla MAYÚS y, a continuación, haga clic en otro encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="c04ca-117">To sort again by an additional column, press and hold the SHIFT key, and then click another column header.</span></span>  
  
-   <span data-ttu-id="c04ca-118">Para seleccionar qué columnas se muestran y cuáles están ocultas, seleccione **Mostrar columnas** en el menú de acceso directo.</span><span class="sxs-lookup"><span data-stu-id="c04ca-118">To select which columns are displayed and which are hidden, select **Show Columns** from the shortcut menu.</span></span>  
  
-   <span data-ttu-id="c04ca-119">Para cambiar el orden en que se muestran las columnas, arrastre cualquier encabezado de columna hacia la izquierda o la derecha.</span><span class="sxs-lookup"><span data-stu-id="c04ca-119">To change the order in which columns are displayed, drag any column header to the left or right.</span></span>  
  
 <span data-ttu-id="c04ca-120">La ventana **Lista de errores** no incluye vínculos a información adicional sobre errores concretos.</span><span class="sxs-lookup"><span data-stu-id="c04ca-120">The **Error List** does not link to additional information about specific errors.</span></span>  
  
## <a name="transact-sql-errors-in-management-studio"></a><span data-ttu-id="c04ca-121">Errores de Transact-SQL en Management Studio</span><span class="sxs-lookup"><span data-stu-id="c04ca-121">Transact-SQL Errors in Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="c04ca-122">muestra los errores para los scripts de [!INCLUDE[tsql](../../includes/tsql-md.md)] en las ubicaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c04ca-122">displays errors for [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts in the following locations:</span></span>  
  
-   <span data-ttu-id="c04ca-123">La ventana **Lista de errores** contiene todos los errores sintácticos y semánticos encontrados por IntelliSense en el Editor de [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c04ca-123">The **Error List** contains all syntax and semantic errors found by IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Editor.</span></span> <span data-ttu-id="c04ca-124">Esta lista de errores se actualiza dinámicamente a medida que se modifican los scripts de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c04ca-124">This list of errors is dynamically updated as you edit [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="c04ca-125">La lista incluye todos los errores encontrados por el editor en cada script de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c04ca-125">The list includes all errors that the editor has found in each [!INCLUDE[tsql](../../includes/tsql-md.md)] script.</span></span> <span data-ttu-id="c04ca-126">El editor no detiene el análisis de un archivo al encontrar errores en un script.</span><span class="sxs-lookup"><span data-stu-id="c04ca-126">The editor does not stop parsing a file after encountering errors in a script.</span></span> <span data-ttu-id="c04ca-127">En [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], IntelliSense en el Editor de [!INCLUDE[ssDE](../../includes/ssde-md.md)] no admite todos los elementos de sintaxis de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c04ca-127">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Editor does not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax elements.</span></span> <span data-ttu-id="c04ca-128">La ventana **Lista de errores** solo contiene los errores de la sintaxis de [!INCLUDE[tsql](../../includes/tsql-md.md)] admitida por IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="c04ca-128">The **Error List** contains only errors from the [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax that is supported by IntelliSense.</span></span>  
  
-   <span data-ttu-id="c04ca-129">La pestaña **Mensajes** de la parte inferior de ventana del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] muestra todos los errores y los mensajes devueltos por [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] al ejecutar un script de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c04ca-129">The **Messages** tab at the bottom of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window displays all errors and messages that are returned by the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] when a [!INCLUDE[tsql](../../includes/tsql-md.md)] script is executed.</span></span> <span data-ttu-id="c04ca-130">Esta lista no cambia hasta que se ejecuta el script de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c04ca-130">This list does not change until you execute the script again.</span></span> <span data-ttu-id="c04ca-131">[!INCLUDE[ssDE](../../includes/ssde-md.md)] detiene el análisis de un lote cuando encuentra uno o dos errores de compilación; por lo tanto, es posible que la pestaña **Mensajes** no incluya todos los errores de un script.</span><span class="sxs-lookup"><span data-stu-id="c04ca-131">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] stops parsing a batch after it finds one or two compile errors; therefore, the **Messages** tab might not list all errors in a script.</span></span>  
  
 <span data-ttu-id="c04ca-132">A veces, los errores aparecen en ambas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="c04ca-132">Sometimes errors are listed in both locations.</span></span> <span data-ttu-id="c04ca-133">Por ejemplo, un archivo de script podría tener un error de sintaxis que apareciese en la ventana **Lista de errores**.</span><span class="sxs-lookup"><span data-stu-id="c04ca-133">For example, a script file might have a syntax error that is listed in the **Error List**.</span></span> <span data-ttu-id="c04ca-134">Si ejecuta el script antes de corregir el error, el analizador de [!INCLUDE[ssDE](../../includes/ssde-md.md)] puede detectar la misma condición y devolver otra copia del mensaje de error en la pestaña **Mensajes** .</span><span class="sxs-lookup"><span data-stu-id="c04ca-134">If you execute the script before you correct the error, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] parser can detect the same condition and return another copy of the error message in the **Messages** tab.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c04ca-135">En **Lista de errores** solo se muestran los errores del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] ; no se muestran los errores de los editores MDX, DMX ni XML/A.</span><span class="sxs-lookup"><span data-stu-id="c04ca-135">The **Error List** only displays errors from the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor; it does not display errors from the MDX, DMX, or XML/A Editors.</span></span> <span data-ttu-id="c04ca-136">Todos los errores de MDX, DMX y XML/A se muestran en la pestaña **Mensajes** de dichos editores.</span><span class="sxs-lookup"><span data-stu-id="c04ca-136">All MDX, DMX, and XML/A errors are displayed in the **Messages** tab in those editors.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="c04ca-137">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c04ca-137">UI element list</span></span>  
 <span data-ttu-id="c04ca-138">Cuando está abierta la ventana **Lista de errores** , la información se muestra en las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c04ca-138">When the **Error List** is open, the information is displayed in the following columns:</span></span>  
  
 <span data-ttu-id="c04ca-139">**Orden predeterminado**</span><span class="sxs-lookup"><span data-stu-id="c04ca-139">**Default Order**</span></span>  
 <span data-ttu-id="c04ca-140">Muestra un entero que indica el orden en el que se generó una entrada.</span><span class="sxs-lookup"><span data-stu-id="c04ca-140">Displays an integer that indicates the order in which an entry was generated.</span></span>  
  
 <span data-ttu-id="c04ca-141">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c04ca-141">**Description**</span></span>  
 <span data-ttu-id="c04ca-142">Muestra el texto de la entrada de error.</span><span class="sxs-lookup"><span data-stu-id="c04ca-142">Displays the text of the error entry.</span></span> <span data-ttu-id="c04ca-143">Las descripciones largas se ajustan a las líneas siguientes.</span><span class="sxs-lookup"><span data-stu-id="c04ca-143">Lengthy descriptions wrap onto additional lines.</span></span>  
  
 <span data-ttu-id="c04ca-144">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="c04ca-144">**File**</span></span>  
 <span data-ttu-id="c04ca-145">Muestra el nombre del archivo de script que generó el error.</span><span class="sxs-lookup"><span data-stu-id="c04ca-145">Displays the name of the script file that generated the error.</span></span>  
  
 <span data-ttu-id="c04ca-146">**Línea**</span><span class="sxs-lookup"><span data-stu-id="c04ca-146">**Line**</span></span>  
 <span data-ttu-id="c04ca-147">Muestra un entero que indica la línea de código que contiene el error.</span><span class="sxs-lookup"><span data-stu-id="c04ca-147">Displays an integer that indicates which line of the code includes the error.</span></span>  
  
 <span data-ttu-id="c04ca-148">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c04ca-148">**Column**</span></span>  
 <span data-ttu-id="c04ca-149">Muestra un entero que indica la posición del error en la línea de código.</span><span class="sxs-lookup"><span data-stu-id="c04ca-149">Displays an integer that indicates the position of the error in the line of code.</span></span>  
  
 <span data-ttu-id="c04ca-150">**Proyecto**</span><span class="sxs-lookup"><span data-stu-id="c04ca-150">**Project**</span></span>  
 <span data-ttu-id="c04ca-151">Muestra el nombre del proyecto que contiene el archivo de script.</span><span class="sxs-lookup"><span data-stu-id="c04ca-151">Displays the name of the project that includes the script file.</span></span>  
