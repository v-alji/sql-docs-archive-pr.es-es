---
title: Ejecución de opciones de consulta (página general) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.general.f1
ms.assetid: 858a0263-2f04-4692-b8bf-63e93c998ead
author: rothja
ms.author: jroth
ms.openlocfilehash: ce3848b51b81f111333ba0e9ac12c96432dd9863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676163"
---
# <a name="query-options-execution-general-page"></a><span data-ttu-id="e1a44-102">Ejecución de Opciones de consulta (página General)</span><span class="sxs-lookup"><span data-stu-id="e1a44-102">Query Options Execution (General Page)</span></span>
  <span data-ttu-id="e1a44-103">Utilice esta página para especificar las opciones de ejecución de las consultas de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1a44-103">Use this page to specify the options for running [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="e1a44-104">Para tener acceso a este cuadro de diálogo, haga clic con el botón derecho en el cuerpo de una ventana del Editor de consultas y haga clic en **Opciones de consulta**.</span><span class="sxs-lookup"><span data-stu-id="e1a44-104">To access this dialog box, right-click the body of a Query Editor window, and then click **Query Options**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="e1a44-105">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="e1a44-105">UI element list</span></span>  
 <span data-ttu-id="e1a44-106">**SET ROWCOUNT**</span><span class="sxs-lookup"><span data-stu-id="e1a44-106">**SET ROWCOUNT**</span></span>  
 <span data-ttu-id="e1a44-107">El valor predeterminado 0 indica que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] esperará a que se reciban todos los resultados.</span><span class="sxs-lookup"><span data-stu-id="e1a44-107">The default value of 0 indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will wait for results until all results are received.</span></span> <span data-ttu-id="e1a44-108">Especifique un valor mayor que 0 si desea que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] detenga la consulta después de obtener el número de filas especificado.</span><span class="sxs-lookup"><span data-stu-id="e1a44-108">Provide a value greater than 0 if you want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to halt the query after obtaining the specified number of rows.</span></span> <span data-ttu-id="e1a44-109">Para desactivar esta opción (de modo que se devuelvan todas las filas), especifique SET ROWCOUNT 0.</span><span class="sxs-lookup"><span data-stu-id="e1a44-109">To turn this option off (so that all rows are returned), specify SET ROWCOUNT 0.</span></span>  
  
 <span data-ttu-id="e1a44-110">**SET TEXTSIZE**</span><span class="sxs-lookup"><span data-stu-id="e1a44-110">**SET TEXTSIZE**</span></span>  
 <span data-ttu-id="e1a44-111">El valor predeterminado, 2.147.483.647 bytes, indica que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] proporcionará un campo de datos completo hasta el límite de los campos de datos `text`, `ntext`, `nvarchar(max)` y `varchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="e1a44-111">The default value of 2,147,483,647 bytes indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will provide a complete data field up to the limit of `text`, `ntext`, `nvarchar(max)`, and `varchar(max)` data fields.</span></span> <span data-ttu-id="e1a44-112">No afecta al tipo de datos XML.</span><span class="sxs-lookup"><span data-stu-id="e1a44-112">It does not affect the XML data type.</span></span> <span data-ttu-id="e1a44-113">Especifique un número menor para limitar los resultados en caso de que los valores sean elevados.</span><span class="sxs-lookup"><span data-stu-id="e1a44-113">Provide a smaller number to limit results in the case of large values.</span></span> <span data-ttu-id="e1a44-114">Las columnas que superen el número especificado se truncarán.</span><span class="sxs-lookup"><span data-stu-id="e1a44-114">Columns greater than the number provided will be truncated.</span></span>  
  
 <span data-ttu-id="e1a44-115">**Tiempo de espera de ejecución**</span><span class="sxs-lookup"><span data-stu-id="e1a44-115">**Execution time-out**</span></span>  
 <span data-ttu-id="e1a44-116">Indica el número de segundos de espera antes de cancelar la consulta.</span><span class="sxs-lookup"><span data-stu-id="e1a44-116">Indicates the number of seconds to wait before canceling the query.</span></span> <span data-ttu-id="e1a44-117">El valor 0 indica una espera infinita o que no hay tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="e1a44-117">A value of 0 indicates an infinite wait, or no time-out.</span></span>  
  
 <span data-ttu-id="e1a44-118">**Separador de lotes**</span><span class="sxs-lookup"><span data-stu-id="e1a44-118">**Batch separator**</span></span>  
 <span data-ttu-id="e1a44-119">Escriba la palabra que utilice para separar instrucciones Transact-SQL en lotes.</span><span class="sxs-lookup"><span data-stu-id="e1a44-119">Type a word that you use to separate Transact-SQL statements into batches.</span></span> <span data-ttu-id="e1a44-120">El separador predeterminado es GO.</span><span class="sxs-lookup"><span data-stu-id="e1a44-120">The default is GO.</span></span>  
  
 <span data-ttu-id="e1a44-121">**De forma predeterminada, abrir nuevas consultas en modo SQLCMD**</span><span class="sxs-lookup"><span data-stu-id="e1a44-121">**By default, open new queries in SQLCMD Mode**</span></span>  
 <span data-ttu-id="e1a44-122">Active esta casilla para abrir nuevas consultas en modo SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="e1a44-122">Select this check box to open new queries in SQLCMD mode.</span></span> <span data-ttu-id="e1a44-123">Esta casilla solo está visible cuando el cuadro de diálogo se abre a través del menú **herramientas** .</span><span class="sxs-lookup"><span data-stu-id="e1a44-123">This check box is visible only when the dialog box is opened through the **Tools** menu.</span></span>  
  
 <span data-ttu-id="e1a44-124">Cuando seleccione esta opción, tenga en cuenta las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="e1a44-124">When you select this option, be aware of the following limitations:</span></span>  
  
-   <span data-ttu-id="e1a44-125">IntelliSense se desactiva en el Editor de consultas de [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1a44-125">IntelliSense in the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor is turned off.</span></span>  
  
-   <span data-ttu-id="e1a44-126">Debido a que el Editor de consultas no se ejecuta desde la línea de comandos, no podrá pasar parámetros de línea de comandos, tales como variables.</span><span class="sxs-lookup"><span data-stu-id="e1a44-126">Because Query Editor does not run from the command line, you cannot pass in command-line parameters such as variables.</span></span>  
  
-   <span data-ttu-id="e1a44-127">Dado que el Editor de consultas no puede responder a comandos del sistema operativo, debe tener cuidado de no ejecutar instrucciones interactivas.</span><span class="sxs-lookup"><span data-stu-id="e1a44-127">Because Query Editor cannot respond to operating-system prompts, you must be careful not to run interactive statements.</span></span>  
  
 <span data-ttu-id="e1a44-128">**Valores predeterminados**</span><span class="sxs-lookup"><span data-stu-id="e1a44-128">**Reset to Default**</span></span>  
 <span data-ttu-id="e1a44-129">Restablece todos los valores de esta página a los valores predeterminados originales.</span><span class="sxs-lookup"><span data-stu-id="e1a44-129">Resets all values on this page to the original default values.</span></span>  
  
  
