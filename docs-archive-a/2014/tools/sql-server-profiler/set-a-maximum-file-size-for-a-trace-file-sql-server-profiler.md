---
title: Establecer un tamaño máximo de archivo para un archivo de seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- maximum file size for traces
- size [SQL Server], trace files
ms.assetid: e86dc4ce-5aa3-4c0d-acb5-c9e8871ed963
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa990c610f7aa8bf82690c8c201c6643eb712191
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747818"
---
# <a name="set-a-maximum-file-size-for-a-trace-file-sql-server-profiler"></a><span data-ttu-id="4a42b-102">Establecer un tamaño máximo de archivo para un archivo de seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="4a42b-102">Set a Maximum File Size for a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="4a42b-103">Utilice el siguiente procedimiento para establecer el tamaño máximo de archivo para un archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4a42b-103">Use the following procedure to set the maximum file size for a trace file.</span></span>  
  
### <a name="to-set-a-maximum-file-size-for-a-trace-file"></a><span data-ttu-id="4a42b-104">Para establecer un tamaño máximo de archivo para un archivo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4a42b-104">To set a maximum file size for a trace file</span></span>  
  
1.  <span data-ttu-id="4a42b-105">En el menú **Archivo** , haga clic en **Nueva seguimiento**y conéctese a una instancia de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a42b-105">On the **File** menu, click **New Trace**, and then connect to an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="4a42b-106">Aparecerá el cuadro de diálogo **Propiedades de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="4a42b-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4a42b-107">Si se selecciona **Iniciar el seguimiento inmediatamente tras realizar la conexión**, el cuadro de diálogo **Propiedades de seguimiento**no aparecerá y, en su lugar, se iniciará el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4a42b-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="4a42b-108">Para desactivar esta configuración, en el menú **Herramientas**, haga clic en **Opciones**y desactive la casilla **Iniciar el seguimiento inmediatamente tras realizar la conexión** .</span><span class="sxs-lookup"><span data-stu-id="4a42b-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="4a42b-109">En el cuadro **Nombre de seguimiento** , escriba un nombre para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4a42b-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="4a42b-110">En el cuadro **Nombre de plantilla**, seleccione una plantilla de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4a42b-110">In the **Template name**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="4a42b-111">Seleccione **Guardar en el archivo**y, a continuación, especifique un archivo en el que almacenar la información del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4a42b-111">Select **Save to file**, and then specify a file to store the trace information.</span></span>  
  
5.  <span data-ttu-id="4a42b-112">En la casilla **Establecer el tamaño máximo de archivo (MB)** , especifique un tamaño máximo de archivo para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4a42b-112">In the **Set maximum file size** check box, specify a maximum file size for the trace.</span></span> <span data-ttu-id="4a42b-113">Cuando el archivo alcanza este tamaño máximo, se dejan de registrar eventos de seguimiento en el archivo.</span><span class="sxs-lookup"><span data-stu-id="4a42b-113">When the file size reaches this maximum, trace events are no longer recorded in this file.</span></span> <span data-ttu-id="4a42b-114">Si selecciona **Habilitar sustitución incremental de archivos** (seleccionada de manera predeterminada), ocurre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4a42b-114">If you select **Enable file rollover** (which is selected by default),the following occurs:</span></span>  
  
     <span data-ttu-id="4a42b-115">La opción de sustitución incremental de archivos hace que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cierre el archivo actual y cree un archivo nuevo al alcanzar el tamaño máximo de archivo.</span><span class="sxs-lookup"><span data-stu-id="4a42b-115">The file rollover option causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to close the current file and create a new file when the maximum file size is reached.</span></span> <span data-ttu-id="4a42b-116">El nuevo archivo tiene el mismo nombre que el archivo anterior, pero se le anexa un número entero al nombre para indicar la secuencia; por ejemplo, si el archivo de seguimiento original se denomina filename_1.trc, el siguiente archivo de seguimiento es filename_2.trc, etc.</span><span class="sxs-lookup"><span data-stu-id="4a42b-116">The new file has the same name as the previous file, but an integer is appended to the name to indicate its sequence; for example, if the original trace file is named filename_1.trc, the next trace file is filename_2.trc, and so on.</span></span> <span data-ttu-id="4a42b-117">Si un archivo existente ya utiliza el nombre asignado a un archivo nuevo de sustitución incremental, el archivo existente se sobrescribe, a menos que sea de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="4a42b-117">If the name assigned to a new rollover file is already used by an existing file, the existing file is overwritten unless it is read-only.</span></span> <span data-ttu-id="4a42b-118">Esta opción de sustitución incremental de archivos está habilitada de forma predeterminada cuando guarda datos de un seguimiento en un archivo.</span><span class="sxs-lookup"><span data-stu-id="4a42b-118">The file rollover option is enabled by default when you are saving trace data to a file.</span></span>  
  
     <span data-ttu-id="4a42b-119">Con la opción de sustitución incremental de archivos activada, el seguimiento continúa hasta que se detiene por otro medio.</span><span class="sxs-lookup"><span data-stu-id="4a42b-119">With the file rollover option on, the trace continues until it is stopped by some other means.</span></span> <span data-ttu-id="4a42b-120">Para detener el seguimiento una vez que se ha alcanzado el límite de tamaño de archivo, deshabilite la opción de sustitución incremental de archivos.</span><span class="sxs-lookup"><span data-stu-id="4a42b-120">To stop the trace after you have reached the file size limit, disable the file rollover option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4a42b-121">El sistema de archivos FAT32 limita los archivos a un poco menos de 4 GB.</span><span class="sxs-lookup"><span data-stu-id="4a42b-121">The FAT32 file system limits files to slightly less than 4 gigabytes (GB).</span></span> <span data-ttu-id="4a42b-122">Cuando el archivo de seguimiento alcanza ese tamaño, el seguimiento se detiene con el error "Espacio insuficiente en disco".</span><span class="sxs-lookup"><span data-stu-id="4a42b-122">When the trace file reaches that size, the trace fails with the error "Not enough disk space."</span></span> <span data-ttu-id="4a42b-123">Para crear archivos de mayor tamaño, utilice el sistema de archivos NTFS.</span><span class="sxs-lookup"><span data-stu-id="4a42b-123">To create larger files, use the NTFS file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a42b-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a42b-124">See Also</span></span>  
 [<span data-ttu-id="4a42b-125">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="4a42b-125">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
