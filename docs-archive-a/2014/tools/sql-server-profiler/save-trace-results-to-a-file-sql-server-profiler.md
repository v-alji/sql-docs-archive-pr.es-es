---
title: Guardar los resultados de un seguimiento en un archivo (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- saving traces
- traces [SQL Server], saving
ms.assetid: ac528747-0c19-4f3d-96f5-44c762a4abed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9644751cda3689cf7b7cb00ec25310bc700ca1c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748403"
---
# <a name="save-trace-results-to-a-file-sql-server-profiler"></a><span data-ttu-id="a015e-102">Guardar los resultados de un seguimiento en un archivo (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="a015e-102">Save Trace Results to a File (SQL Server Profiler)</span></span>
  <span data-ttu-id="a015e-103">En este tema se describe cómo utilizar el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]para guardar los resultados de un seguimiento en un archivo.</span><span class="sxs-lookup"><span data-stu-id="a015e-103">This topic describes how to save trace results to a file by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-save-trace-results-to-a-file"></a><span data-ttu-id="a015e-104">Para guardar los resultados de un seguimiento en un archivo</span><span class="sxs-lookup"><span data-stu-id="a015e-104">To save trace results to a file</span></span>  
  
1.  <span data-ttu-id="a015e-105">En el menú **Archivo** , haga clic en **Nuevo seguimiento**y conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a015e-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="a015e-106">Aparecerá el cuadro de diálogo **Propiedades de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="a015e-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a015e-107">Si se selecciona **Iniciar el seguimiento inmediatamente tras realizar la conexión**, el cuadro de diálogo **Propiedades de seguimiento**no aparecerá y, en su lugar, se iniciará el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a015e-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="a015e-108">Para desactivar esta configuración, en el menú **Herramientas**, haga clic en **Opciones**y desactive la casilla **Iniciar el seguimiento inmediatamente tras realizar la conexión** .</span><span class="sxs-lookup"><span data-stu-id="a015e-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="a015e-109">En el cuadro **Nombre de seguimiento** , escriba un nombre para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a015e-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="a015e-110">Active la casilla **Guardar en el archivo** .</span><span class="sxs-lookup"><span data-stu-id="a015e-110">Select the **Save to file** check box.</span></span>  
  
     <span data-ttu-id="a015e-111">Aparece el cuadro de diálogo **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="a015e-111">The **Save As**dialog box appears.</span></span>  
  
4.  <span data-ttu-id="a015e-112">En el cuadro de diálogo **Guardar como**, especifique una ruta de acceso y un nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="a015e-112">Specify a path and filename in the **Save As**dialog box.</span></span> <span data-ttu-id="a015e-113">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a015e-113">Click **Save.**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a015e-114">Asegúrese de que el servicio SQL Server tiene los permisos necesarios para escribir en un archivo en el directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="a015e-114">Ensure that the SQL Server service has sufficient permissions to write to a file in the directory specified.</span></span>  
  
5.  <span data-ttu-id="a015e-115">En el cuadro de diálogo **Propiedades de seguimiento** , en el cuadro de texto **Establecer el tamaño máximo de archivo (MB)** , especifique el tamaño máximo del archivo.</span><span class="sxs-lookup"><span data-stu-id="a015e-115">In the **Trace Properties** dialog box, enter the maximum file size in the **Set maximum file size (MB)** text box.</span></span> <span data-ttu-id="a015e-116">El valor predeterminado es 5 megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="a015e-116">The default value is 5 megabytes (MB).</span></span>  
  
6.  <span data-ttu-id="a015e-117">Opcionalmente, especifique las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a015e-117">Optionally, specify the following options:</span></span>  
  
    -   <span data-ttu-id="a015e-118">Active la casilla **Habilitar sustitución incremental de archivos** para que el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] cree archivos para los datos del seguimiento si se alcanza el tamaño máximo del archivo.</span><span class="sxs-lookup"><span data-stu-id="a015e-118">Select the **Enable file rollover** check box to have [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] create new files for trace data once the maximum file size is reached.</span></span> <span data-ttu-id="a015e-119">Esta opción está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a015e-119">This option is selected by default.</span></span>  
  
    -   <span data-ttu-id="a015e-120">Active la casilla **El servidor procesa los datos de seguimiento** para asegurarse de que el servidor registra todos los eventos del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a015e-120">Select the **Server processes trace data** check box to ensure that the server records each trace event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a015e-121">Cuando la casilla **El servidor procesa los datos de seguimiento**está desactivada, el servidor no registra los eventos si con ello el rendimiento disminuye considerablemente.</span><span class="sxs-lookup"><span data-stu-id="a015e-121">When **Server processes trace data**is cleared, the server does not record events if recording events significantly degrades performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a015e-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a015e-122">See Also</span></span>  
 [<span data-ttu-id="a015e-123">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="a015e-123">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
