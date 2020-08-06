---
title: 'Herramienta de administración de la línea de comandos: SqlLocalDB.exe | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_location:
- sqluserinstance.dll
ms.assetid: dd0882b1-a8a9-447a-8bdf-0f9d7f36d336
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d21a6a8879e981e52bd2e7d3bd05a37e65d8cf4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663493"
---
# <a name="command-line-management-tool-sqllocaldbexe"></a><span data-ttu-id="abe57-102">Herramienta de administración de la línea de comandos: SqlLocalDB.exe</span><span class="sxs-lookup"><span data-stu-id="abe57-102">Command-Line Management Tool: SqlLocalDB.exe</span></span>
  <span data-ttu-id="abe57-103">SqlLocalDB.exe es una sencilla herramienta que permite al usuario administrar con facilidad instancias de LocalDB desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="abe57-103">SqlLocalDB.exe is a simple tool that enables the user to easily manage LocalDB instances from the command line.</span></span> <span data-ttu-id="abe57-104">Se implementa como un contenedor simple en la API de instancia de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="abe57-104">It is implemented as a simple wrapper around the LocalDB instance API.</span></span> <span data-ttu-id="abe57-105">Como en numerosas herramientas de SQL Server similares (por ejemplo, SQLCMD), los parámetros se pasan a SqlLocalDB como argumentos de la línea de comandos y la salida se envía a la consola.</span><span class="sxs-lookup"><span data-stu-id="abe57-105">As in many similar SQL Server tools (for example, SQLCMD), parameters are passed to SqlLocalDB as command-line arguments and output is sent to the console.</span></span>  
  
 <span data-ttu-id="abe57-106">SqlLocalDB permite a los desarrolladores de software usar LocalDB sin tener que escribir código para llamar a la API o sin depender en otras herramientas para que hagan el trabajo por ellos.</span><span class="sxs-lookup"><span data-stu-id="abe57-106">SqlLocalDB enables developers to use LocalDB without having to write code to call the API or depend on other tools to do it for them.</span></span>  
  
## <a name="sqllocaldb-options"></a><span data-ttu-id="abe57-107">Opciones de SqlLocalDB</span><span class="sxs-lookup"><span data-stu-id="abe57-107">SqlLocalDB Options</span></span>  
 <span data-ttu-id="abe57-108">SqlLocalDB admite las opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="abe57-108">SqlLocalDB supports the following options.</span></span>  
  
|<span data-ttu-id="abe57-109">Opción</span><span class="sxs-lookup"><span data-stu-id="abe57-109">Option</span></span>|<span data-ttu-id="abe57-110">Qué hace</span><span class="sxs-lookup"><span data-stu-id="abe57-110">What it does</span></span>|  
|------------|------------------|  
|`-?`|<span data-ttu-id="abe57-111">Imprime texto de ayuda.</span><span class="sxs-lookup"><span data-stu-id="abe57-111">Prints help text.</span></span>|  
|`create&#124;c "instance name" [version-number] [-s]`|<span data-ttu-id="abe57-112">Crea una instancia de LocalDB con un nombre y una versión determinados.</span><span class="sxs-lookup"><span data-stu-id="abe57-112">Creates a new LocalDB instance with a specified name and version.</span></span><br /><br /> <span data-ttu-id="abe57-113">Si se omite el parámetro [versión-número], toma el valor predeterminado de la versión de compilación de SqlLocalDB.</span><span class="sxs-lookup"><span data-stu-id="abe57-113">If the [version-number] parameter is omitted, it defaults to the SqlLocalDB build version.</span></span><br /><br /> <span data-ttu-id="abe57-114">-s inicia la nueva instancia de LocalDB una vez se haya creado.</span><span class="sxs-lookup"><span data-stu-id="abe57-114">-s starts the new LocalDB instance after it is created.</span></span>|  
|`delete&#124;d "instance name"`|<span data-ttu-id="abe57-115">Elimina la instancia de LocalDB con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="abe57-115">Deletes the LocalDB instance with the specified name.</span></span>|  
|`start&#124;s "instance name"`|<span data-ttu-id="abe57-116">Inicia la instancia de LocalDB con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="abe57-116">Starts the LocalDB instance with the specified name.</span></span>|  
|`stop&#124;p "instance name" [-i&#124;-k]`|<span data-ttu-id="abe57-117">Detiene la instancia de LocalDB con el nombre especificado, cuando las consultas actuales terminan de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="abe57-117">Stops the LocalDB instance with the specified name, after current queries finish running.</span></span><br /><br /> <span data-ttu-id="abe57-118">-i solicita el cierre de la instancia de LocalDB con la opción de NOWAIT.</span><span class="sxs-lookup"><span data-stu-id="abe57-118">-i requests the LocalDB instance shutdown with the NOWAIT option.</span></span><br /><br /> <span data-ttu-id="abe57-119">-k elimina el proceso de la instancia de LocalDB sin ponerse en contacto con ella.</span><span class="sxs-lookup"><span data-stu-id="abe57-119">-k kills the LocalDB instance process without contacting it.</span></span>|  
|`share&#124;h ["owner SID or account"] "private name" "shared name"`|<span data-ttu-id="abe57-120">Comparte la instancia privada especificada con el nombre compartido especificado.</span><span class="sxs-lookup"><span data-stu-id="abe57-120">Shares the specified private instance using the specified shared name.</span></span> <span data-ttu-id="abe57-121">Si se omite el SID del usuario o el nombre de la cuenta, usa de forma predeterminada el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="abe57-121">If the user SID or account name is omitted, it defaults to the current user.</span></span>|  
|`unshare&#124;u "shared name"`|<span data-ttu-id="abe57-122">No comparte la instancia compartida de LocalDB especificada.</span><span class="sxs-lookup"><span data-stu-id="abe57-122">Unshares the specified shared LocalDB instance.</span></span>|  
|`info&#124;i`|<span data-ttu-id="abe57-123">Enumera todas las instancias existentes de LocalDB que son propiedad del usuario actual y todas las instancias de LocalDB compartidas.</span><span class="sxs-lookup"><span data-stu-id="abe57-123">Lists all existing LocalDB instances that are owned by the current user and all shared LocalDB instances.</span></span>|  
|`info&#124;i "instance name"`|<span data-ttu-id="abe57-124">Imprime información sobre la instancia de LocalDB especificada.</span><span class="sxs-lookup"><span data-stu-id="abe57-124">Prints the information about the specified LocalDB instance.</span></span>|  
|`versions&#124;v`|<span data-ttu-id="abe57-125">Enumera todas las versiones de LocalDB que se hayan instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="abe57-125">Lists all LocalDB versions installed on the computer.</span></span>|  
|||  
|`trace&#124;t on&#124;off`|<span data-ttu-id="abe57-126">Activa y desactiva el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="abe57-126">Turns tracing on and off.</span></span>|  
  
 <span data-ttu-id="abe57-127">SqlLocalDB trata los espacios como delimitadores; debe escribir entre comillas los nombres de instancia que contienen espacios y caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="abe57-127">SqlLocalDB treats spaces as delimiters; you must surround the instance names that contain spaces and special characters with quotes.</span></span> <span data-ttu-id="abe57-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abe57-128">For example:</span></span>  
  
 `SqlLocalDB create "My instance name with spaces"`  
  
  
