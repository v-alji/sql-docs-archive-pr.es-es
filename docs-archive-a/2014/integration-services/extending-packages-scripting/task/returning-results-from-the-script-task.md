---
title: Devolver los resultados de la tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], status information
- ExecutionValue property
- status information [Integration Services]
- TaskResult property
- SSIS Script task, status information
ms.assetid: ac06805b-c2db-44bd-af5c-5a0debe36dd7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bef3e93644377f715b5ad24e0a53df053197a03a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745901"
---
# <a name="returning-results-from-the-script-task"></a><span data-ttu-id="34a9f-102">Devolver los resultados de la tarea Script</span><span class="sxs-lookup"><span data-stu-id="34a9f-102">Returning Results from the Script Task</span></span>
  <span data-ttu-id="34a9f-103">La tarea Script utiliza las propiedades <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> y <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> opcional para devolver información de estado al módulo ejecutable de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que se puede utilizar para determinar la ruta de acceso del flujo de trabajo después de que la tarea Script ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="34a9f-103">The Script task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> and the optional <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> properties to return status information to the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime that can be used to determine the path of the workflow after the Script task has finished.</span></span>  
  
## <a name="taskresult"></a><span data-ttu-id="34a9f-104">TaskResult</span><span class="sxs-lookup"><span data-stu-id="34a9f-104">TaskResult</span></span>  
 <span data-ttu-id="34a9f-105">La propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> notifica si la tarea tuvo éxito o no.</span><span class="sxs-lookup"><span data-stu-id="34a9f-105">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> property reports whether the task succeeded or failed.</span></span> <span data-ttu-id="34a9f-106">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="34a9f-106">For example:</span></span>  
  
 `Dts.TaskResult = ScriptResults.Success`  
  
## <a name="executionvalue"></a><span data-ttu-id="34a9f-107">ExecutionValue</span><span class="sxs-lookup"><span data-stu-id="34a9f-107">ExecutionValue</span></span>  
 <span data-ttu-id="34a9f-108">La propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> devuelve, de manera opcional, un objeto definido por el usuario que cuantifica o proporciona más información sobre si se ha realizado correctamente la tarea Script o ha dado un error.</span><span class="sxs-lookup"><span data-stu-id="34a9f-108">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> property optionally returns a user-defined object that quantifies or provides more information about the success or failure of the Script task.</span></span> <span data-ttu-id="34a9f-109">Por ejemplo, la tarea FTP utiliza la propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> para devolver el número de archivos transferidos.</span><span class="sxs-lookup"><span data-stu-id="34a9f-109">For example, the FTP task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> property to return the number of files transferred.</span></span> <span data-ttu-id="34a9f-110">La tarea Ejecutar SQL devuelve el número de filas afectadas por la tarea.</span><span class="sxs-lookup"><span data-stu-id="34a9f-110">The Execute SQL task returns the number of rows affected by the task.</span></span> <span data-ttu-id="34a9f-111"><xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> también se puede utilizar para determinar la ruta de acceso del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="34a9f-111">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> can also be used to determine the path of the workflow.</span></span> <span data-ttu-id="34a9f-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="34a9f-112">For example:</span></span>  
  
 `Dim rowsAffected as Integer`  
  
 `...`  
  
 `rowsAffected = 1000`  
  
 `Dts.ExecutionValue = rowsAffected`  
  
<span data-ttu-id="34a9f-113">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="34a9f-113">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="34a9f-114">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="34a9f-114">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="34a9f-115">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="34a9f-115">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="34a9f-116">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="34a9f-116">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
