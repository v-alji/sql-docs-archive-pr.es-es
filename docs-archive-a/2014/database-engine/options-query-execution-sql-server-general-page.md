---
title: Opciones (ejecución de consultas-SQL Server-página general) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryExecution.SqlServer.SqlExecutionGeneral
ms.assetid: 3f8d59bc-3f97-4e5d-8b86-5ac670d20780
author: rothja
ms.author: jroth
ms.openlocfilehash: eaa95293636d02674fb720dcd1b8146279f78e72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676637"
---
# <a name="options-query-execution-sql-server-general-page"></a><span data-ttu-id="932a5-102">Opciones (ejecución de consultas-SQL Server-página general)</span><span class="sxs-lookup"><span data-stu-id="932a5-102">Options (Query Execution-SQL Server-General Page)</span></span>
  <span data-ttu-id="932a5-103">Utilice esta página para especificar las opciones de ejecución de las consultas de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="932a5-103">Use this page to specify the options for running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="932a5-104">Los cambios que se realicen en estas opciones solo se aplicarán a las nuevas consultas de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="932a5-104">Changes to these options are only applied to new [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="932a5-105">Para cambiar las opciones de una consulta actual, haga clic en **Opciones de consulta** en el menú **Consulta** o, en una ventana Consulta de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], haga clic con el botón derecho y seleccione **Opciones de consulta**.</span><span class="sxs-lookup"><span data-stu-id="932a5-105">To change the options for a current query, click **Query Options** on the **Query** menu, or in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window right-click and select **Query Options**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="932a5-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="932a5-106">Options</span></span>  
 <span data-ttu-id="932a5-107">**SET ROWCOUNT**</span><span class="sxs-lookup"><span data-stu-id="932a5-107">**SET ROWCOUNT**</span></span>  
 <span data-ttu-id="932a5-108">El valor predeterminado 0 indica que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] esperará a que se reciban todos los resultados.</span><span class="sxs-lookup"><span data-stu-id="932a5-108">The default value of 0 indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will wait for results until all results are received.</span></span> <span data-ttu-id="932a5-109">Especifique un valor mayor que 0 si desea que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] detenga la consulta después de obtener el número de filas especificado.</span><span class="sxs-lookup"><span data-stu-id="932a5-109">Provide a value greater than 0 if you want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to halt the query after obtaining the specified number of rows.</span></span> <span data-ttu-id="932a5-110">Para desactivar esta opción (de modo que se devuelvan todas las filas), especifique SET ROWCOUNT 0.</span><span class="sxs-lookup"><span data-stu-id="932a5-110">To turn this option off (so that all rows are returned), specify SET ROWCOUNT 0.</span></span>  
  
 <span data-ttu-id="932a5-111">**SET TEXTSIZE**</span><span class="sxs-lookup"><span data-stu-id="932a5-111">**SET TEXTSIZE**</span></span>  
 <span data-ttu-id="932a5-112">El valor predeterminado de 2.147.483.647 bytes indica que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] proporcionará campos de datos completos hasta el límite de los campos de datos `text` y `ntext`.</span><span class="sxs-lookup"><span data-stu-id="932a5-112">The default value of 2,147,483,647 bytes indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will provide complete data fields up to the limit of `text` and `ntext` data fields.</span></span> <span data-ttu-id="932a5-113">Especifique un número menor para limitar los resultados en caso de que los valores sean elevados.</span><span class="sxs-lookup"><span data-stu-id="932a5-113">Provide a smaller number to limit results in the case of large values.</span></span> <span data-ttu-id="932a5-114">Las columnas que superen el número especificado se truncarán.</span><span class="sxs-lookup"><span data-stu-id="932a5-114">Columns greater than the number provided will be truncated.</span></span>  
  
 <span data-ttu-id="932a5-115">**Tiempo de espera de ejecución**</span><span class="sxs-lookup"><span data-stu-id="932a5-115">**Execution time-out**</span></span>  
 <span data-ttu-id="932a5-116">Establece el valor predeterminado en el cuadro de diálogo **Nueva conexión** .</span><span class="sxs-lookup"><span data-stu-id="932a5-116">Sets the default value in the **New Connection** dialog box.</span></span> <span data-ttu-id="932a5-117">Utilice este cuadro de número para indicar a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] el número de segundos que debe esperar antes de cancelar la consulta.</span><span class="sxs-lookup"><span data-stu-id="932a5-117">Use this spin box to tell [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] the number of seconds to wait before canceling the query.</span></span> <span data-ttu-id="932a5-118">Un valor de 0 indica una espera infinita o ningún tiempo de espera. Este valor es 0 en una nueva instalación.</span><span class="sxs-lookup"><span data-stu-id="932a5-118">A value of 0 indicates an infinite wait, or no time-out. This value is 0 on a new installation.</span></span>  
  
 <span data-ttu-id="932a5-119">**Separador de lotes**</span><span class="sxs-lookup"><span data-stu-id="932a5-119">**Batch separator**</span></span>  
 <span data-ttu-id="932a5-120">Escriba la palabra que utilice para separar instrucciones [!INCLUDE[tsql](../includes/tsql-md.md)] en lotes.</span><span class="sxs-lookup"><span data-stu-id="932a5-120">Type a word that you use to separate [!INCLUDE[tsql](../includes/tsql-md.md)] statements into batches.</span></span> <span data-ttu-id="932a5-121">El separador predeterminado es GO.</span><span class="sxs-lookup"><span data-stu-id="932a5-121">The default is GO.</span></span>  
  
 <span data-ttu-id="932a5-122">**De forma predeterminada, abrir nuevas consultas en modo SQLCMD**</span><span class="sxs-lookup"><span data-stu-id="932a5-122">**By default, open new queries in SQLCMD Mode**</span></span>  
 <span data-ttu-id="932a5-123">Active esta casilla para abrir nuevas consultas en modo SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="932a5-123">Select this check box to open new queries in SQLCMD mode.</span></span> <span data-ttu-id="932a5-124">Para obtener más información sobre el modo SQLCMD, consulte [Modificar scripts SQLCMD con el Editor de consultas](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="932a5-124">For more information about SQLCMD mode, see [Edit SQLCMD Scripts with Query Editor](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md).</span></span>  
  
 <span data-ttu-id="932a5-125">Cuando seleccione esta opción, tenga en cuenta las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="932a5-125">When you select this option, be aware of the following limitations:</span></span>  
  
-   <span data-ttu-id="932a5-126">IntelliSense se desactiva en el Editor de consultas de [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="932a5-126">IntelliSense in the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor is turned off.</span></span>  
  
-   <span data-ttu-id="932a5-127">Debido a que el Editor de consultas no se ejecuta desde la línea de comandos, no podrá pasar parámetros de línea de comandos, tales como variables.</span><span class="sxs-lookup"><span data-stu-id="932a5-127">Because Query Editor does not run from the command line, you cannot pass in command-line parameters such as variables.</span></span>  
  
-   <span data-ttu-id="932a5-128">Dado que el Editor de consultas no puede responder a comandos del sistema operativo, debe tener cuidado de no ejecutar instrucciones interactivas.</span><span class="sxs-lookup"><span data-stu-id="932a5-128">Because Query Editor cannot respond to operating-system prompts, you must be careful not to run interactive statements.</span></span>  
  
 <span data-ttu-id="932a5-129">**Valores predeterminados**</span><span class="sxs-lookup"><span data-stu-id="932a5-129">**Reset to Default**</span></span>  
 <span data-ttu-id="932a5-130">Haga clic en esta opción para restablecer todos los valores de esta página a los valores predeterminados originales.</span><span class="sxs-lookup"><span data-stu-id="932a5-130">Click to reset all values on this page to the original default values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="932a5-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="932a5-131">See Also</span></span>  
 [<span data-ttu-id="932a5-132">Utilidad sqlcmd</span><span class="sxs-lookup"><span data-stu-id="932a5-132">sqlcmd Utility</span></span>](../tools/sqlcmd-utility.md)  
  
  
