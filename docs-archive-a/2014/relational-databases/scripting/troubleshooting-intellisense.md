---
title: Solución de problemas IntelliSense
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- unavailable options [IntelliSense]
- IntelliSense [SQL Server], troubleshooting
- IntelliSense [SQL Server], unavailable options
- troubleshooting [IntelliSense]
ms.assetid: 4b72ffc6-aea2-4e11-ab36-fa2de4d7bcc5
author: rothja
ms.author: jroth
ms.openlocfilehash: 087baf616fc215c480ae78621623cbe1ed512b57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746863"
---
# <a name="troubleshooting-intellisense-sql-server-management-studio"></a><span data-ttu-id="a8a55-102">Solución de problemas IntelliSense (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a8a55-102">Troubleshooting IntelliSense (SQL Server Management Studio)</span></span>
  <span data-ttu-id="a8a55-103">Hay algunos casos en que es posible que las opciones de IntelliSense no funcionen como se espera.</span><span class="sxs-lookup"><span data-stu-id="a8a55-103">There are certain cases when the IntelliSense options might not work as you expect.</span></span>  
  
## <a name="conditions-that-affect-intellisense"></a><span data-ttu-id="a8a55-104">Condiciones que afectan a IntelliSense</span><span class="sxs-lookup"><span data-stu-id="a8a55-104">Conditions That Affect IntelliSense</span></span>  
 <span data-ttu-id="a8a55-105">Las condiciones siguientes pueden afectar al comportamiento de IntelliSense:</span><span class="sxs-lookup"><span data-stu-id="a8a55-105">The following conditions might affect the behavior of IntelliSense:</span></span>  
  
-   <span data-ttu-id="a8a55-106">Hay un error de código encima del cursor.</span><span class="sxs-lookup"><span data-stu-id="a8a55-106">There is a code error above the cursor.</span></span>  
  
     <span data-ttu-id="a8a55-107">Si hay una instrucción incompleta u otro error de código encima de la ubicación del punto de inserción, es posible que IntelliSense no pueda analizar los elementos del código y que, por lo tanto, no funcione.</span><span class="sxs-lookup"><span data-stu-id="a8a55-107">If there is an incomplete statement or other coding error above the location of the insertion point, IntelliSense may be unable to parse the code elements, and therefore will not work.</span></span> <span data-ttu-id="a8a55-108">Para volver a habilitar IntelliSense, puede marcar con comentarios el código aplicable.</span><span class="sxs-lookup"><span data-stu-id="a8a55-108">You can comment out the applicable code to enable IntelliSense again.</span></span>  
  
-   <span data-ttu-id="a8a55-109">El punto de inserción está dentro de un comentario de código.</span><span class="sxs-lookup"><span data-stu-id="a8a55-109">The insertion point is inside a code comment.</span></span>  
  
     <span data-ttu-id="a8a55-110">Las opciones de IntelliSense no están disponibles cuando el punto de inserción está dentro de un comentario del archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="a8a55-110">IntelliSense options are not available when the insertion point is within a comment in your source file.</span></span>  
  
-   <span data-ttu-id="a8a55-111">El punto de inserción está dentro de un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="a8a55-111">The insertion point is inside a string literal.</span></span>  
  
     <span data-ttu-id="a8a55-112">Las opciones de IntelliSense no están disponibles cuando el punto de inserción está dentro de las comillas de un literal de cadena; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a8a55-112">IntelliSense options are not available when the insertion point is inside the quotation marks around a string literal, for example:</span></span>  
  
     `WHERE FirstName LIKE 'Patri%|'`  
  
-   <span data-ttu-id="a8a55-113">Las opciones automáticas están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="a8a55-113">The automatic options are turned off.</span></span>  
  
     <span data-ttu-id="a8a55-114">La mayoría de las características de IntelliSense funcionan automáticamente de forma predeterminada. No obstante, se pueden deshabilitar todas.</span><span class="sxs-lookup"><span data-stu-id="a8a55-114">Many IntelliSense features work automatically by default, but you can disable any feature.</span></span>  
  
     <span data-ttu-id="a8a55-115">Es posible usar las características de IntelliSense aunque la finalización de instrucciones automática esté deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="a8a55-115">Even when automatic statement completion is disabled, you can use an IntelliSense feature.</span></span> <span data-ttu-id="a8a55-116">Para obtener más información, vea [Configurar IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="a8a55-116">For more information, see [Configure IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span></span>  
  
## <a name="database-engine-query-intellisense"></a><span data-ttu-id="a8a55-117">IntelliSense en las consultas de Database Engine</span><span class="sxs-lookup"><span data-stu-id="a8a55-117">Database Engine Query IntelliSense</span></span>  
 <span data-ttu-id="a8a55-118">Los problemas siguientes se aplican al Editor de consultas de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="a8a55-118">The following issues apply to the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] Query Editor:</span></span>  
  
-   <span data-ttu-id="a8a55-119">La funcionalidad IntelliSense del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] no es compatible con todos los elementos de sintaxis de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8a55-119">The IntelliSense functionality of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor does not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax elements.</span></span> <span data-ttu-id="a8a55-120">La ayuda sobre parámetros no es compatible con los parámetros de algunos objetos, como los procedimientos almacenados extendidos.</span><span class="sxs-lookup"><span data-stu-id="a8a55-120">Parameter help does not support the parameters in some objects, such as extended stored procedures.</span></span> <span data-ttu-id="a8a55-121">Para obtener más información, vea [Sintaxis de Transact-SQL compatible con IntelliSense](transact-sql-syntax-supported-by-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="a8a55-121">For more information, see [Transact-SQL Syntax Supported by IntelliSense](transact-sql-syntax-supported-by-intellisense.md).</span></span>  
  
-   <span data-ttu-id="a8a55-122">IntelliSense solamente está disponible cuando el Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] está conectado a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] o posterior.</span><span class="sxs-lookup"><span data-stu-id="a8a55-122">IntelliSense is only available when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor is connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] from [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span> <span data-ttu-id="a8a55-123">IntelliSense no está disponible cuando el Editor de consultas está conectado a versiones anteriores del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8a55-123">IntelliSense is not available when the Query Editor is connected to earlier versions of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="a8a55-124">IntelliSense se desactiva en el Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] cuando está activado el modo SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="a8a55-124">IntelliSense is turned off in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor when the SQLCMD mode is set on.</span></span>  
  
-   <span data-ttu-id="a8a55-125">La funcionalidad de IntelliSense no abarca a los objetos de base de datos creados por otra conexión después de que la ventana del editor se conecte a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a8a55-125">IntelliSense functionality does not cover database objects created by another connection after your editor window connected to the database.</span></span> <span data-ttu-id="a8a55-126">Si faltan objetos de las características de IntelliSense tales como las listas de finalización, puede elegir uno de estos tres mecanismos si desea actualizar la memoria caché de objetos para la ventana del editor:</span><span class="sxs-lookup"><span data-stu-id="a8a55-126">If objects are missing from IntelliSense features such as completion lists, you can choose one of these three mechanisms to refresh the cache of objects for your editor window:</span></span>  
  
    -   <span data-ttu-id="a8a55-127">Seleccione el menú **Edición** , seleccione **IntelliSense**y, a continuación, seleccione **Actualizar caché local**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-127">Select the **Edit** menu, select **IntelliSense**, then select **Refresh Local Cache**.</span></span>  
  
    -   <span data-ttu-id="a8a55-128">Utilice el método abreviado de teclado CTRL+Mayús+R.</span><span class="sxs-lookup"><span data-stu-id="a8a55-128">Use the CTRL+Shift+R keyboard shortcut.</span></span>  
  
    -   <span data-ttu-id="a8a55-129">Desconecte la ventana del editor de la instancia [!INCLUDE[ssDE](../../includes/ssde-md.md)] y vuelva a conectarla.</span><span class="sxs-lookup"><span data-stu-id="a8a55-129">Disconnect your editor window from the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and reconnect.</span></span>  
  
-   <span data-ttu-id="a8a55-130">Las listas de finalización no incluyen los objetos de base de datos para los que no tiene permisos.</span><span class="sxs-lookup"><span data-stu-id="a8a55-130">Completion lists do not include database objects for which you do not have permissions.</span></span> <span data-ttu-id="a8a55-131">IntelliSense marca las referencias a los objetos para los que tiene permisos.</span><span class="sxs-lookup"><span data-stu-id="a8a55-131">IntelliSense flags references to objects for which you do have permissions.</span></span> <span data-ttu-id="a8a55-132">Por ejemplo, si abre un script que ha escrito otra persona, cualquier referencia a los objetos para los que esa persona tenga permisos y usted no se marca como incorrecta.</span><span class="sxs-lookup"><span data-stu-id="a8a55-132">For example, if you open a script that is written by someone else, any references to objects for which that person has permissions and you do not are flagged as incorrect.</span></span>  
  
-   <span data-ttu-id="a8a55-133">Las listas de finalización podrían dejar de funcionar si pierde la conexión a la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8a55-133">Completion lists might stop working if you lose the connection to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="a8a55-134">Vuelva a conectarse a la instancia.</span><span class="sxs-lookup"><span data-stu-id="a8a55-134">Reconnect to the instance.</span></span>  
  
  
