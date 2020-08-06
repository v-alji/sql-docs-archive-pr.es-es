---
title: Conectar con el servidor (página Parámetros de conexión adicionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttoserver.options.registeredservers.f1
ms.assetid: ba34b01a-6289-4eb8-8341-fa3d9ec87b3f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5c6a23df6a6b9ea324d54fd270f5aa2269471ed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677867"
---
# <a name="connect-to-server-additional-connection-parameters-page"></a><span data-ttu-id="d5acf-102">Conectar con el servidor (página Parámetros de conexión adicionales)</span><span class="sxs-lookup"><span data-stu-id="d5acf-102">Connect to Server (Additional Connection Parameters Page)</span></span>
  <span data-ttu-id="d5acf-103">El cuadro de diálogo \*\*Conectar con[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] de \*\* presenta los valores de cadena de conexión más comunes como opciones.</span><span class="sxs-lookup"><span data-stu-id="d5acf-103">The **Connect to** dialog box of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] presents the most common connection string values as options.</span></span> <span data-ttu-id="d5acf-104">Utilice la página **Parámetros de conexión adicionales** para agregar más parámetros de conexión a la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="d5acf-104">Use the **Additional Connection Parameters** page to add more connection parameters to the connection string.</span></span>  
  
-   <span data-ttu-id="d5acf-105">Los parámetros de conexión adicionales pueden ser cualquier parámetro de conexión ODBC.</span><span class="sxs-lookup"><span data-stu-id="d5acf-105">Additional connection parameters can be any ODBC connection parameter.</span></span>  
  
-   <span data-ttu-id="d5acf-106">Los parámetros de conexión adicionales se deberían agregar con el formato **;parameter1=value1;parameter2=value2**.</span><span class="sxs-lookup"><span data-stu-id="d5acf-106">Additional connection parameters should be added in the format **;parameter1=value1;parameter2=value2**.</span></span>  
  
-   <span data-ttu-id="d5acf-107">Los parámetros que se agregan utilizando la página **Parámetros de conexión adicionales** se agregan a los parámetros seleccionados utilizando las opciones del cuadro de diálogo **Conectar a** .</span><span class="sxs-lookup"><span data-stu-id="d5acf-107">Parameters added using the **Additional Connection Parameters** page are added to the parameters selected using the **Connect to** dialog box options.</span></span>  
  
-   <span data-ttu-id="d5acf-108">La última instancia de cada parámetro proporcionado invalida cualquier instancia anterior del mismo.</span><span class="sxs-lookup"><span data-stu-id="d5acf-108">The last instance of each parameter provided overrides any previous instances of the parameter.</span></span> <span data-ttu-id="d5acf-109">Los parámetros que se agregan con la página **Parámetros de conexión adicionales** siguen y reemplazan a los parámetros proporcionados en las pestañas **Inicio de sesión** o **Propiedades de conexión** .</span><span class="sxs-lookup"><span data-stu-id="d5acf-109">Parameters added using the **Additional Connection Parameters** page follow and replace the parameters provided in the **Login** or **Connection Properties** tabs.</span></span> <span data-ttu-id="d5acf-110">Por ejemplo, si la pestaña **Inicio de sesión** proporciona **SERVER1** como **Nombre del servidor**y la página **Parámetros de conexión adicionales** contiene **;SERVER=SERVER2**, la conexión se realizará a **SERVER2**.</span><span class="sxs-lookup"><span data-stu-id="d5acf-110">For example, if the **Login** tab provides **SERVER1** as the **Server name**, and the **Additional Connection Parameters** page contains **;SERVER=SERVER2**, the connection will be made to **SERVER2**.</span></span>  
  
-   <span data-ttu-id="d5acf-111">Los parámetros que se agregan utilizando la página **Parámetros de conexión adicionales** siempre se pasan como texto simple.</span><span class="sxs-lookup"><span data-stu-id="d5acf-111">Parameters added using the **Additional Connection Parameters** page are always passed as plain text.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d5acf-112">No incluya credenciales de inicio de sesión y contraseñas en la página **Parámetros de conexión adicionales** .</span><span class="sxs-lookup"><span data-stu-id="d5acf-112">Do not include login credentials and passwords in the **Additional Connection Parameters** page.</span></span> <span data-ttu-id="d5acf-113">No se cifrarán cuando se pasen a través de la red.</span><span class="sxs-lookup"><span data-stu-id="d5acf-113">They will not be encrypted when they are passed across the network.</span></span> <span data-ttu-id="d5acf-114">En su lugar, use la pestaña **Inicio de sesión** .</span><span class="sxs-lookup"><span data-stu-id="d5acf-114">Use the **Login** tab instead.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="d5acf-115">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="d5acf-115">Task List</span></span>  
  
### <a name="to-show-the-additional-connection-parameters-page"></a><span data-ttu-id="d5acf-116">Para mostrar la página Parámetros de conexión adicionales</span><span class="sxs-lookup"><span data-stu-id="d5acf-116">To show the Additional Connection Parameters page</span></span>  
  
1.  <span data-ttu-id="d5acf-117">En [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], en el menú **Consulta** , seleccione **Conexión**y haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="d5acf-117">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], on the **Query** menu, point to **Connection**, and then click **Connect**.</span></span>  
  
2.  <span data-ttu-id="d5acf-118">En el cuadro de diálogo **Conectar a** , haga clic en **Opciones**y en la pestaña **Parámetros de conexión adicionales** .</span><span class="sxs-lookup"><span data-stu-id="d5acf-118">In the **Connect to** dialog box, click **Options**, and then click the **Additional Connection Parameters** tab.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d5acf-119">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d5acf-119">Examples</span></span>  
  
### <a name="example-a-connecting-to-the-database-engine"></a><span data-ttu-id="d5acf-120">Ejemplo A: conectarse al motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="d5acf-120">Example A: Connecting to the Database Engine</span></span>  
 <span data-ttu-id="d5acf-121">Para conectarse a la base de datos [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] en un servidor denominado ACCOUNTING, escriba lo siguiente en la página **Parámetros de conexión adicionales** :</span><span class="sxs-lookup"><span data-stu-id="d5acf-121">To connect to the [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] database on a server named ACCOUNTING, enter the following in the **Additional connection parameters** page:</span></span>  
  
```  
;SERVER=ACCOUNTING;DATABASE=AdventureWorks2012  
```  
  
### <a name="example-b-connecting-to-analysis-services"></a><span data-ttu-id="d5acf-122">Ejemplo B: conectarse a Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d5acf-122">Example B: Connecting to Analysis Services</span></span>  
 <span data-ttu-id="d5acf-123">Para conectarse a Analysis Services, hacer que todas las particiones que escuchan las notificaciones se consulten en tiempo real (omitiendo el almacenamiento en memoria caché) y establecer el valor de tiempo de espera de reescritura en 5, escriba lo siguiente en la página **Parámetros de conexión adicionales** :</span><span class="sxs-lookup"><span data-stu-id="d5acf-123">To connect to the Analysis Servers and cause all the partitions listening for notifications to be queried as real time (bypassing caching), and to set the writeback time out value to 5, enter the following in the **Additional connection parameters** page:</span></span>  
  
```  
;Real Time Olap=TRUE;Writeback Timeout=5  
```  
  
  
