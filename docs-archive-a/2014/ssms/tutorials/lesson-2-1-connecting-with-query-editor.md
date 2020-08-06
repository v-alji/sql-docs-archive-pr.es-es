---
title: Conectar con el Editor de consultas | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 48725f54-a7b6-4b79-948e-965c1fe4eef1
author: stevestein
ms.author: sstein
ms.openlocfilehash: b50783450dfb9516c78a465806ee322d7a575377
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674502"
---
# <a name="connecting-with-query-editor"></a><span data-ttu-id="c7daa-102">Conectar con el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="c7daa-102">Connecting with Query Editor</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="c7daa-103">permite escribir o editar código sin estar conectado al servidor.</span><span class="sxs-lookup"><span data-stu-id="c7daa-103">permits you to write or edit code while disconnected from the server.</span></span> <span data-ttu-id="c7daa-104">Esto puede ser útil cuando el servidor no está disponible o cuando se desea preservar los escasos recursos de la red o el servidor.</span><span class="sxs-lookup"><span data-stu-id="c7daa-104">This can be useful when the server is not available or when you want to conserve scarce server or network resources.</span></span> <span data-ttu-id="c7daa-105">También puede cambiar la conexión del Editor de consultas a una instancia nueva de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sin abrir una ventana nueva del Editor de consultas o volver a escribir código.</span><span class="sxs-lookup"><span data-stu-id="c7daa-105">You can also change the connection of Query Editor to a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without opening a new Query Editor window or retyping your code.</span></span>  
  
## <a name="coding-offline"></a><span data-ttu-id="c7daa-106">Escribir código sin conexión</span><span class="sxs-lookup"><span data-stu-id="c7daa-106">Coding Offline</span></span>  
  
#### <a name="to-write-code-offline-and-then-connect-to-different-servers"></a><span data-ttu-id="c7daa-107">Para escribir código sin conexión y conectarse posteriormente a servidores diferentes</span><span class="sxs-lookup"><span data-stu-id="c7daa-107">To write code offline and then connect to different servers</span></span>  
  
1.  <span data-ttu-id="c7daa-108">En la barra de herramientas de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , haga clic en **Consulta de motor de base de datos** para abrir el Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="c7daa-108">On the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] toolbar, click **Database Engine Query** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="c7daa-109">En el cuadro de diálogo **Conectar al motor de base de datos** , haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="c7daa-109">In the **Connect to Database Engine** dialog box, click **Cancel**.</span></span> <span data-ttu-id="c7daa-110">Se abrirá el Editor de consultas y la barra de título indicará que el usuario no está conectado a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7daa-110">The Query Editor opens, and the title bar for the Query Editor indicates that you are not connected to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="c7daa-111">En el panel de código, escriba las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] siguientes:</span><span class="sxs-lookup"><span data-stu-id="c7daa-111">In the code pane, type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    SELECT * FROM Production.Product;  
    GO  
    ```  
  
     <span data-ttu-id="c7daa-112">En este punto, se puede conectar a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] haciendo clic en **Conectar**, **Ejecutar**, **Analizar**o **Mostrar plan de ejecución estimado**. Todas estas opciones están disponibles en el menú **Consulta** , en la barra de herramientas del Editor de consultas o bien en el menú contextual al hacer clic con el botón derecho en la ventana del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="c7daa-112">At this point you can connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by clicking **Connect**, **Execute**, **Parse**, or **Display Estimated Execution Plan**, all of which are available from either the **Query** menu, the Query Editor toolbar, or from the shortcut menu when you right-click in the Query Editor window.</span></span> <span data-ttu-id="c7daa-113">En esta práctica, se utilizará la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="c7daa-113">For this practice, we'll use the toolbar.</span></span>  
  
4.  <span data-ttu-id="c7daa-114">En la barra de herramientas, haga clic en el botón **Ejecutar** para abrir el cuadro de diálogo **Conectar al motor de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="c7daa-114">On the toolbar, click the **Execute** button to open the **Connect to Database Engine** dialog box.</span></span>  
  
5.  <span data-ttu-id="c7daa-115">En el cuadro de texto **Nombre de servidor** , escriba un nombre y, a continuación, haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="c7daa-115">In the **Server name** text box, type your server name, and then click **Options**.</span></span>  
  
6.  <span data-ttu-id="c7daa-116">En la lista **Conectar con base de datos** de la pestaña **Propiedades de conexión** , seleccione [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] y, a continuación, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="c7daa-116">On the **Connection Properties** tab, in the **Connect to database** list, browse the server to select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] and then click **Connect**.</span></span>  
  
7.  <span data-ttu-id="c7daa-117">Para abrir otra ventana del Editor de consultas con la misma conexión, haga clic en la opción **Nueva consulta**de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="c7daa-117">To open another Query Editor window with the same connection, on the toolbar click **New Query**.</span></span>  
  
8.  <span data-ttu-id="c7daa-118">Para cambiar conexiones, haga clic con el botón derecho en la ventana del Editor de consultas, seleccione **Conexión**y, después, haga clic en **Cambiar conexión**.</span><span class="sxs-lookup"><span data-stu-id="c7daa-118">To change connections, right-click in the Query Editor window, point to **Connection**, and then click **Change Connection**.</span></span>  
  
9. <span data-ttu-id="c7daa-119">En el cuadro de diálogo **Conectar a SQL Server** , seleccione otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si está disponible y, a continuación, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="c7daa-119">In the **Connect to SQL Server** dialog box, select another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if available, and then click **Connect**.</span></span>  
  
 <span data-ttu-id="c7daa-120">Esta nueva función del Editor de consultas permite ejecutar fácilmente el mismo código en varios servidores.</span><span class="sxs-lookup"><span data-stu-id="c7daa-120">This new feature of Query Editor enables you to easily run the same code on several servers.</span></span> <span data-ttu-id="c7daa-121">Esto puede resultar útil para realizar tareas de mantenimiento que afecten a servidores similares.</span><span class="sxs-lookup"><span data-stu-id="c7daa-121">This may be useful for maintenance actions involving similar servers.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c7daa-122">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="c7daa-122">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c7daa-123">Agregar sangría</span><span class="sxs-lookup"><span data-stu-id="c7daa-123">Adding Indentation</span></span>](lesson-2-2-adding-indentation.md)  
  
  
