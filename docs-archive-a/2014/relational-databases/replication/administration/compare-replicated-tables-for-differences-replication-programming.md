---
title: Comparar tablas replicadas para buscar diferencias (programación de la replicación) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- tablediff utility
- comparing replicated tables
ms.assetid: cd253a17-0c85-42b4-912c-690169ebe799
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0d804c7d4ac9cc54fa144b7054c6032663b76c0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750801"
---
# <a name="compare-replicated-tables-for-differences-replication-programming"></a><span data-ttu-id="52104-102">Comparar tablas replicadas para buscar diferencias (programación de la replicación)</span><span class="sxs-lookup"><span data-stu-id="52104-102">Compare Replicated Tables for Differences (Replication Programming)</span></span>
  <span data-ttu-id="52104-103">Para determinar si los datos publicados en los artículos de tabla del publicador y el suscriptor no son idénticos, lo que puede indicar una falta de convergencia, se usa la validación de artículos.</span><span class="sxs-lookup"><span data-stu-id="52104-103">Article validation is used to determine if published data for table articles at the Publisher and Subscriber are not identical, which can indicate non-convergence.</span></span> <span data-ttu-id="52104-104">Para obtener más información, vea [Validar datos replicados](../validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="52104-104">For more information, see [Validate Replicated Data](../validate-data-at-the-subscriber.md).</span></span> <span data-ttu-id="52104-105">La validación, sin embargo, solo devuelve información sobre la existencia o no de diferencias, pero no indica las diferencias concretas entre las tablas de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="52104-105">However, validation only returns pass or fail information and does not provide any information about what is different between the source and destination tables.</span></span> <span data-ttu-id="52104-106">La utilidad de símbolo del sistema **tablediff** devuelve información detallada sobre las diferencias entre dos tablas y puede generar un script [!INCLUDE[tsql](../../../includes/tsql-md.md)] para establecer la convergencia de la suscripción con los datos del publicador.</span><span class="sxs-lookup"><span data-stu-id="52104-106">The **tablediff** command prompt utility returns detailed difference information between two tables and can even generate a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script to bring a subscription into convergence with data at the Publisher.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52104-107">La utilidad **tablediff** solo se admite en servidores [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52104-107">The **tablediff** utility is only supported for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] servers.</span></span>  
  
### <a name="to-compare-replicated-tables-for-differences-using-tablediff"></a><span data-ttu-id="52104-108">Para buscar diferencias en tablas replicarse con tablediff</span><span class="sxs-lookup"><span data-stu-id="52104-108">To compare replicated tables for differences using tablediff</span></span>  
  
1.  <span data-ttu-id="52104-109">En el símbolo del sistema de cualquier servidor incluido en una topología de replicación, ejecute la [tablediff Utility](../../../tools/tablediff-utility.md).</span><span class="sxs-lookup"><span data-stu-id="52104-109">From the command prompt at any server in a replication topology, run the [tablediff Utility](../../../tools/tablediff-utility.md).</span></span> <span data-ttu-id="52104-110">Especifique los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="52104-110">Specify the following parameters:</span></span>  
  
    -   <span data-ttu-id="52104-111">**-sourceserver** : el nombre del servidor donde se sabe que los datos son correctos, normalmente el publicador.</span><span class="sxs-lookup"><span data-stu-id="52104-111">**-sourceserver** - name of the server on which the data is known to be correct, usually the Publisher.</span></span>  
  
    -   <span data-ttu-id="52104-112">**-sourcedatabase** : el nombre de la base de datos que contiene los datos correctos.</span><span class="sxs-lookup"><span data-stu-id="52104-112">**-sourcedatabase** - name of the database containing the correct data.</span></span>  
  
    -   <span data-ttu-id="52104-113">**-sourcetable** : el nombre de la tabla de origen del artículo que se compara.</span><span class="sxs-lookup"><span data-stu-id="52104-113">**-sourcetable** - name of the source table for the article being compared.</span></span>  
  
    -   <span data-ttu-id="52104-114">(Opcional) **-sourceschema** : el propietario del esquema de la tabla de origen, si no se trata del esquema predeterminado.</span><span class="sxs-lookup"><span data-stu-id="52104-114">(Optional) **-sourceschema** - schema owner of the source table, if not the default schema.</span></span>  
  
    -   <span data-ttu-id="52104-115">(Opcional) **-sourceuser** y **-sourcepassword** si se usa la autenticación de SQL Server para conectar al publicador.</span><span class="sxs-lookup"><span data-stu-id="52104-115">(Optional) **-sourceuser** and **-sourcepassword** when using SQL Server Authentication to connect to the Publisher.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="52104-116">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="52104-116">When possible, use Windows Authentication.</span></span> <span data-ttu-id="52104-117">Si debe usar la autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , pida a los usuarios que escriban las credenciales de seguridad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="52104-117">If you must use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="52104-118">Si debe almacenar las credenciales en un archivo de script, proteja el archivo para evitar el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="52104-118">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
    -   <span data-ttu-id="52104-119">**-destinationserver** : el nombre del servidor en el que se comparan los datos, normalmente un suscriptor.</span><span class="sxs-lookup"><span data-stu-id="52104-119">**-destinationserver** - name of the server on which the data is being compared, usually a Subscriber.</span></span>  
  
    -   <span data-ttu-id="52104-120">**-destinationdatabase** : el nombre de la base de datos que se compara.</span><span class="sxs-lookup"><span data-stu-id="52104-120">**-destinationdatabase** - name of a the database being compared.</span></span>  
  
    -   <span data-ttu-id="52104-121">**-destinationtable** : el nombre de la tabla que se compara.</span><span class="sxs-lookup"><span data-stu-id="52104-121">**-destinationtable** - name of the table being compared.</span></span>  
  
    -   <span data-ttu-id="52104-122">(Opcional) **-destinationschema** : el propietario del esquema de la tabla de destino, si no se trata del esquema predeterminado.</span><span class="sxs-lookup"><span data-stu-id="52104-122">(Optional) **-destinationschema** - schema owner of the destination table, if not the default schema.</span></span>  
  
    -   <span data-ttu-id="52104-123">(Opcional) **-destinationuser** y **-destinationpassword** si usa la autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para conectar al suscriptor.</span><span class="sxs-lookup"><span data-stu-id="52104-123">(Optional) **-destinationuser** and **-destinationpassword** when using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication to connect to the Subscriber.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="52104-124">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="52104-124">When possible, use Windows Authentication.</span></span> <span data-ttu-id="52104-125">Si debe usar la autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , pida a los usuarios que escriban las credenciales de seguridad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="52104-125">If you must use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="52104-126">Si debe almacenar las credenciales en un archivo de script, proteja el archivo para evitar el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="52104-126">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
    -   <span data-ttu-id="52104-127">(Opcional) Use **-c** para realizar una comparación de columna.</span><span class="sxs-lookup"><span data-stu-id="52104-127">(Optional) Use **-c** to do a column-level comparison.</span></span>  
  
    -   <span data-ttu-id="52104-128">(Opcional) Use **-q** para realizar una comparación rápida solo del esquema y de recuento de filas.</span><span class="sxs-lookup"><span data-stu-id="52104-128">(Optional) Use **-q** to do a fast, row count- and schema-only comparison.</span></span>  
  
    -   <span data-ttu-id="52104-129">(Opcional) Especifique un nombre de archivo y una ruta de acceso en **-o** para generar los resultados en un archivo.</span><span class="sxs-lookup"><span data-stu-id="52104-129">(Optional) Specify a file name and path for **-o** to output the results to a file.</span></span>  
  
    -   <span data-ttu-id="52104-130">(Opcional) Especifique una tabla de la base de datos de suscripciones en la que insertar los resultados de **-et**.</span><span class="sxs-lookup"><span data-stu-id="52104-130">(Optional) Specify a table in the subscription database into which to insert results for **-et**.</span></span> <span data-ttu-id="52104-131">Si la tabla ya existe, especifique **-dt** para quitarla previamente.</span><span class="sxs-lookup"><span data-stu-id="52104-131">If the table already exists, specify **-dt** to first drop the table.</span></span>  
  
    -   <span data-ttu-id="52104-132">(Opcional) Use **-f** para generar un archivo [!INCLUDE[tsql](../../../includes/tsql-md.md)] y corregir los datos en el suscriptor de forma que coincidan con los datos en el publicador.</span><span class="sxs-lookup"><span data-stu-id="52104-132">(Optional) Use **-f** to generate a [!INCLUDE[tsql](../../../includes/tsql-md.md)] file to fix data at the Subscriber so that it matches data at the Publisher.</span></span> <span data-ttu-id="52104-133">Use **-df** para especificar el número de instrucciones [!INCLUDE[tsql](../../../includes/tsql-md.md)] de cada archivo.</span><span class="sxs-lookup"><span data-stu-id="52104-133">Use **-df** to specify the number of [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements in each file.</span></span>  
  
    -   <span data-ttu-id="52104-134">(Opcional) Use **-rc** y **-ri** para especificar el número de veces que se intentará una operación y el intervalo de reintento.</span><span class="sxs-lookup"><span data-stu-id="52104-134">(Optional) Use **-rc** and **-ri** to specify the number of times to retry an operation and the retry interval.</span></span>  
  
    -   <span data-ttu-id="52104-135">(Opcional) Use **-strict** para exigir la comparación estricta del esquema entre las tablas de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="52104-135">(Optional) Use **-strict** to enforce strict schema comparison between source and destination tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52104-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52104-136">See Also</span></span>  
 [<span data-ttu-id="52104-137">Validar datos en el suscriptor</span><span class="sxs-lookup"><span data-stu-id="52104-137">Validate Data at the Subscriber</span></span>](../validate-data-at-the-subscriber.md)  
  
  
