---
title: Conectarse al motor de base de datos con sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sqlcmd utility, Database Engine connections
- Named Pipes [SQL Server], sqlcmd utility
- TCP/IP [SQL Server], client protocols
- network protocols [SQL Server], sqlcmd utility
- protocols [SQL Server], sqlcmd utility
- VIA
- client protocols [SQL Server]
ms.assetid: 74b0fb71-7f8e-4171-9431-d07528532524
author: rothja
ms.author: jroth
ms.openlocfilehash: 3b409683b651e3e6508baced5eb3bc9fcc631e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669585"
---
# <a name="connect-to-the-database-engine-with-sqlcmd"></a><span data-ttu-id="b706e-102">Conectarse al motor de base de datos con sqlcmd</span><span class="sxs-lookup"><span data-stu-id="b706e-102">Connect to the Database Engine With sqlcmd</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b706e-103">permite las comunicaciones de clientes con el protocolo de red TCP/IP (valor predeterminado) y el protocolo de canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="b706e-103">supports client communication with the TCP/IP network protocol (the default), and the named pipes protocol.</span></span> <span data-ttu-id="b706e-104">El protocolo de memoria compartida también está disponible si el cliente se está conectando a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="b706e-104">The shared memory protocol is also available if the client is connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the same computer.</span></span> <span data-ttu-id="b706e-105">Hay varios métodos habituales para seleccionar el protocolo.</span><span class="sxs-lookup"><span data-stu-id="b706e-105">There are three common methods of selecting the protocol.</span></span> <span data-ttu-id="b706e-106">El protocolo que la utilidad **sqlcmd** utiliza se determina en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="b706e-106">The protocol used by the **sqlcmd** utility is determined in the following order:</span></span>  
  
-   <span data-ttu-id="b706e-107">**sqlcmd** usa el protocolo especificado como parte de la cadena de conexión, como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="b706e-107">**sqlcmd** uses the protocol specified as part of the connection string as described below.</span></span>  
  
-   <span data-ttu-id="b706e-108">Si no se especifica ningún protocolo como parte de la cadena de conexión, **sqlcmd** usará el protocolo definido como parte del alias al que se está conectando.</span><span class="sxs-lookup"><span data-stu-id="b706e-108">If no protocol is specified as part the connection string, **sqlcmd** will use the protocol defined as part of the alias that it is connecting to.</span></span> <span data-ttu-id="b706e-109">Para configurar **sqlcmd** para usar un protocolo de red específico al crear un alias, vea [Crear o eliminar un alias de servidor para que lo use un cliente &#40;Administrador de configuración de SQL Server&#41;](../../database-engine/configure-windows/create-or-delete-a-server-alias-for-use-by-a-client.md).</span><span class="sxs-lookup"><span data-stu-id="b706e-109">To configure **sqlcmd** to use a specific network protocol by creating an alias, see [Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/create-or-delete-a-server-alias-for-use-by-a-client.md).</span></span>  
  
-   <span data-ttu-id="b706e-110">Si el protocolo no se especifica de otra forma, **sqlcmd** usará el protocolo de red determinado por el orden de protocolos en el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b706e-110">If the protocol is not specified in some other way, **sqlcmd** will use the network protocol determined by the protocol order in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
 <span data-ttu-id="b706e-111">En los siguientes ejemplos se muestran diversas formas de conectarse a la instancia predeterminada de [!INCLUDE[ssDE](../../includes/ssde-md.md)] en el puerto 1433, mientras que se supone que las instancias con nombre de [!INCLUDE[ssDE](../../includes/ssde-md.md)] están escuchando en el puerto 1691.</span><span class="sxs-lookup"><span data-stu-id="b706e-111">The following examples show various ways of connecting to the default instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] on port 1433, and named instances of [!INCLUDE[ssDE](../../includes/ssde-md.md)] presumed to be listening on port 1691.</span></span> <span data-ttu-id="b706e-112">En algunos de estos ejemplos se utiliza la dirección IP del adaptador de bucle invertido (127.0.0.1).</span><span class="sxs-lookup"><span data-stu-id="b706e-112">Some of these examples use the IP address of the loopback adapter (127.0.0.1).</span></span> <span data-ttu-id="b706e-113">Pruebe el uso de la dirección IP de la tarjeta de interfaz de red del equipo.</span><span class="sxs-lookup"><span data-stu-id="b706e-113">Test using the IP address of your computer network interface card.</span></span>  
  
 <span data-ttu-id="b706e-114">Conéctese al [!INCLUDE[ssDE](../../includes/ssde-md.md)] especificando el nombre de la instancia:</span><span class="sxs-lookup"><span data-stu-id="b706e-114">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the instance name:</span></span>  
  
```  
sqlcmd -S ComputerA  
sqlcmd -S ComputerA\instanceB  
```  
  
 <span data-ttu-id="b706e-115">Conéctese a [!INCLUDE[ssDE](../../includes/ssde-md.md)] especificando la dirección IP:</span><span class="sxs-lookup"><span data-stu-id="b706e-115">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the IP address:</span></span>  
  
```  
sqlcmd -S 127.0.0.1  
sqlcmd -S 127.0.0.1\instanceB  
```  
  
 <span data-ttu-id="b706e-116">Conéctese a [!INCLUDE[ssDE](../../includes/ssde-md.md)] especificando el número de puerto TCP\IP:</span><span class="sxs-lookup"><span data-stu-id="b706e-116">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the TCP\IP port number:</span></span>  
  
```  
sqlcmd -S ComputerA,1433  
sqlcmd -S ComputerA,1691  
sqlcmd -S 127.0.0.1,1433  
sqlcmd -S 127.0.0.1,1691  
```  
  
### <a name="to-connect-using-tcpip"></a><span data-ttu-id="b706e-117">Para conectarse utilizando TCP/IP</span><span class="sxs-lookup"><span data-stu-id="b706e-117">To connect using TCP/IP</span></span>  
  
-   <span data-ttu-id="b706e-118">Conéctese mediante la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b706e-118">Connect using the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S tcp:<computer name>,<port number>  
    ```  
  
-   <span data-ttu-id="b706e-119">Conéctese a la instancia predeterminada:</span><span class="sxs-lookup"><span data-stu-id="b706e-119">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S tcp:ComputerA,1433  
    sqlcmd -S tcp:127.0.0.1,1433  
    ```  
  
-   <span data-ttu-id="b706e-120">Conéctese a una instancia con nombre:</span><span class="sxs-lookup"><span data-stu-id="b706e-120">Connect to a named instance:</span></span>  
  
    ```  
    sqlcmd -S tcp:ComputerA,1691  
    sqlcmd -S tcp:127.0.0.1,1691  
    ```  
  
### <a name="to-connect-using-named-pipes"></a><span data-ttu-id="b706e-121">Para conectarse mediante canalizaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="b706e-121">To connect using named pipes</span></span>  
  
-   <span data-ttu-id="b706e-122">Conéctese utilizando una de las sintaxis generales siguientes:</span><span class="sxs-lookup"><span data-stu-id="b706e-122">Connect using one of the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S np:\\<computer name>\<pipe name>  
    ```  
  
-   <span data-ttu-id="b706e-123">Conéctese a la instancia predeterminada:</span><span class="sxs-lookup"><span data-stu-id="b706e-123">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S np:\\ComputerA\pipe\sql\query  
    sqlcmd -S np:\\127.0.0.1\pipe\sql\query  
    ```  
  
-   <span data-ttu-id="b706e-124">Conéctese a una instancia con nombre:</span><span class="sxs-lookup"><span data-stu-id="b706e-124">Connect to a named instance instance:</span></span>  
  
    ```  
    sqlcmd -S np:\\ComputerA\pipe\MSSQL$<instancename>\sql\query  
    sqlcmd -S np:\\127.0.0.1\pipe\MSSQL$<instancename>\sql\query  
    ```  
  
### <a name="to-connect-using-shared-memory-a-local-procedure-call-from-a-client-on-the-server"></a><span data-ttu-id="b706e-125">Para conectarse mediante la memoria compartida (una llamada a un procedimiento local) desde un cliente en el servidor</span><span class="sxs-lookup"><span data-stu-id="b706e-125">To connect using shared memory (a local procedure call) from a client on the server</span></span>  
  
-   <span data-ttu-id="b706e-126">Conéctese utilizando una de las sintaxis generales siguientes:</span><span class="sxs-lookup"><span data-stu-id="b706e-126">Connect using one of the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S lpc:<computer name>  
    ```  
  
-   <span data-ttu-id="b706e-127">Conéctese a la instancia predeterminada:</span><span class="sxs-lookup"><span data-stu-id="b706e-127">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S lpc:ComputerA  
    ```  
  
-   <span data-ttu-id="b706e-128">Conéctese a una instancia con nombre:</span><span class="sxs-lookup"><span data-stu-id="b706e-128">Connect to a named instance:</span></span>  
  
    ```  
    sqlcmd -S lpc:ComputerA\<instancename>  
    ```  
  
  
