---
title: Guardar los resultados de un seguimiento en una tabla (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- saving traces
- traces [SQL Server], saving
ms.assetid: edbecf74-683b-4e43-a1ef-7a3d5f5e27f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 08acfb4e7136f8b28d1c990d508b8578f96a57b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748392"
---
# <a name="save-trace-results-to-a-table-sql-server-profiler"></a><span data-ttu-id="937d1-102">Guardar los resultados de un seguimiento en una tabla (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="937d1-102">Save Trace Results to a Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="937d1-103">En este tema se describe cómo utilizar el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]para guardar los resultados de un seguimiento en una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="937d1-103">This topic describes how to save trace results to a database table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-save-trace-results-to-a-table"></a><span data-ttu-id="937d1-104">Para guardar los resultados de un seguimiento en una tabla</span><span class="sxs-lookup"><span data-stu-id="937d1-104">To save trace results to a table</span></span>  
  
1.  <span data-ttu-id="937d1-105">En el menú **Archivo** , haga clic en **Nuevo seguimiento**y conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="937d1-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="937d1-106">Aparecerá el cuadro de diálogo **Propiedades de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="937d1-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="937d1-107">Si se selecciona **Iniciar el seguimiento inmediatamente tras realizar la conexión**, el cuadro de diálogo **Propiedades de seguimiento**no aparecerá y, en su lugar, se iniciará el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="937d1-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="937d1-108">Para desactivar esta configuración, en el menú **Herramientas**, haga clic en **Opciones**y desactive la casilla **Iniciar el seguimiento inmediatamente tras realizar la conexión** .</span><span class="sxs-lookup"><span data-stu-id="937d1-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="937d1-109">En el cuadro **Nombre de seguimiento** , escriba un nombre para el seguimiento y haga clic en **Guardar en la tabla**.</span><span class="sxs-lookup"><span data-stu-id="937d1-109">In the **Trace name** box, type a name for the trace, and then click **Save to table**.</span></span>  
  
3.  <span data-ttu-id="937d1-110">En el cuadro de diálogo **Conectar al servidor** , conéctese a la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contendrá la tabla de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="937d1-110">In the **Connect to server** dialog box, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that will contain the trace table.</span></span>  
  
4.  <span data-ttu-id="937d1-111">En el cuadro **Tabla de destino** , seleccione una base de datos de la lista **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="937d1-111">In the **Destination Table** dialog box, select a database from the **Database**list.</span></span>  
  
5.  <span data-ttu-id="937d1-112">En la lista **Propietario** , seleccione el propietario del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="937d1-112">In the **Owner** list, select the owner for the trace.</span></span>  
  
6.  <span data-ttu-id="937d1-113">En la lista **Tabla** , escriba o seleccione el nombre de tabla para los resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="937d1-113">In the **Table** list, type or select the table name for the trace results.</span></span> <span data-ttu-id="937d1-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="937d1-114">Click **OK.**</span></span>  
  
7.  <span data-ttu-id="937d1-115">En el cuadro de diálogo **propiedades de seguimiento** , active la casilla establecer número **máximo de filas (en miles)** para especificar el número máximo de filas que se van a guardar.</span><span class="sxs-lookup"><span data-stu-id="937d1-115">In the **Trace Properties** dialog box, select the **Set maximum rows (in thousands)** check box to specify the maximum number of rows to save.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="937d1-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="937d1-116">See Also</span></span>  
 [<span data-ttu-id="937d1-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="937d1-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
