---
title: Cuadro de diálogo Guardar script de cambio (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.generatechangescript
- vdtsql.chm:65544
ms.assetid: fc9d1639-5efa-44fe-a04f-4d4d0def2833
author: stevestein
ms.author: sstein
ms.openlocfilehash: 19a2bb2ce9a219c195421e2efa203fc115e1ae1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743820"
---
# <a name="save-change-script-dialog-box-visual-database-tools"></a><span data-ttu-id="fd64c-102">Guardar script de cambio (cuadro de diálogo, Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="fd64c-102">Save Change Script Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="fd64c-103">Este cuadro de diálogo muestra el script [!INCLUDE[tsql](../../includes/tsql-md.md)] de los cambios que ha realizado desde que se guardó la tabla por última vez.</span><span class="sxs-lookup"><span data-stu-id="fd64c-103">This dialog box shows the [!INCLUDE[tsql](../../includes/tsql-md.md)] script for the changes you have made since you last saved the table.</span></span> <span data-ttu-id="fd64c-104">Permite guardar el script en un archivo de texto en la ubicación que elija.</span><span class="sxs-lookup"><span data-stu-id="fd64c-104">It also allows you to save the script to a text file at a location you choose.</span></span>  
  
 <span data-ttu-id="fd64c-105">Puede tener acceso a este cuadro de diálogo después de realizar cambios sin guardarlos en una tabla del Diseñador de tablas.</span><span class="sxs-lookup"><span data-stu-id="fd64c-105">You can access this dialog box after you have made unsaved changes to a table in Table Designer.</span></span> <span data-ttu-id="fd64c-106">En el menú **Diseñador de tablas** , haga clic en **Generar script de cambio**.</span><span class="sxs-lookup"><span data-stu-id="fd64c-106">On the **Table Designer** menu, click **Generate Change Script**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd64c-107">Los scripts de cambio proporcionados por Visual Database Tools no incluyen ningún control de errores.</span><span class="sxs-lookup"><span data-stu-id="fd64c-107">Change scripts provided by Visual Database Tools contain no error handling.</span></span> <span data-ttu-id="fd64c-108">Asumen que los objetos de base de datos no han cambiado desde que se abrió la herramienta y que, por lo tanto, no habrá problemas relacionados con los cambios.</span><span class="sxs-lookup"><span data-stu-id="fd64c-108">They assume that database objects have not changed since the tool was opened, and that change-related problems will therefore not occur.</span></span> <span data-ttu-id="fd64c-109">Antes de ejecutar un script de cambio, debe incluir las instrucciones de control de errores apropiadas.</span><span class="sxs-lookup"><span data-stu-id="fd64c-109">Before running a change script, you should include the appropriate error-handling statements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fd64c-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="fd64c-110">Options</span></span>  
 <span data-ttu-id="fd64c-111">**Generar automáticamente script de cambio al guardar**</span><span class="sxs-lookup"><span data-stu-id="fd64c-111">**Automatically generate change script on every save**</span></span>  
 <span data-ttu-id="fd64c-112">Si esta opción está activada, el cuadro de diálogo **Guardar script de cambio** aparecerá cada vez que guarde los cambios en una tabla.</span><span class="sxs-lookup"><span data-stu-id="fd64c-112">If checked, the **Save Change Script** dialog box will appear any time you save changes to a table.</span></span>  
  
 <span data-ttu-id="fd64c-113">**Sí**</span><span class="sxs-lookup"><span data-stu-id="fd64c-113">**Yes**</span></span>  
 <span data-ttu-id="fd64c-114">Abre el cuadro de diálogo **Guardar** , en el que puede elegir la ubicación del archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="fd64c-114">Bring up the **Save** dialog box where you can choose the location for the text file.</span></span>  
  
 <span data-ttu-id="fd64c-115">**No**</span><span class="sxs-lookup"><span data-stu-id="fd64c-115">**No**</span></span>  
 <span data-ttu-id="fd64c-116">Cancela la creación del script de cambio.</span><span class="sxs-lookup"><span data-stu-id="fd64c-116">Cancel the creation of the change script.</span></span>  
  
  
