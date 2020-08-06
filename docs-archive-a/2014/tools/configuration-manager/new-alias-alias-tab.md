---
title: Nuevo alias (pestaña alias) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 785eb6fb-f67e-449d-b1c8-c38dfbb95ef6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 90742e5de3da0cac83c8b18eebba242ddb9a865d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672330"
---
# <a name="new-alias-alias-tab"></a><span data-ttu-id="5547e-102">Nuevo alias (pestaña Alias)</span><span class="sxs-lookup"><span data-stu-id="5547e-102">New Alias (Alias Tab)</span></span>
  <span data-ttu-id="5547e-103">Un alias es un nombre alternativo que se puede utilizar para establecer una conexión.</span><span class="sxs-lookup"><span data-stu-id="5547e-103">An alias is an alternate name that can be used to make a connection.</span></span> <span data-ttu-id="5547e-104">El alias encapsula los elementos necesarios de una cadena de conexión y los expone con un nombre elegido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5547e-104">The alias encapsulates the required elements of a connection string, and exposes them with a name chosen by the user.</span></span> <span data-ttu-id="5547e-105">Use la página **Alias** del cuadro de diálogo **Alias - Nuevo** para especificar los elementos de la cadena de conexión de un alias.</span><span class="sxs-lookup"><span data-stu-id="5547e-105">Use the **Alias** page on the **Alias - New** dialog box to specify the elements of the connection string for an alias.</span></span> <span data-ttu-id="5547e-106">Para cambiar la cadena de conexión de un alias existente, vea [Propiedades de &#60;Alias&#62; &#40;pestaña Alias&#41;](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md).</span><span class="sxs-lookup"><span data-stu-id="5547e-106">To change the connection string of an existing alias, see [&#60;Alias&#62; Properties &#40;Alias Tab&#41;](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md).</span></span>  
  
 <span data-ttu-id="5547e-107">No es necesario completar todos los valores de la cuadrícula **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="5547e-107">All values in the **Properties** grid do not have to be completed.</span></span> <span data-ttu-id="5547e-108">Las combinaciones válidas varían en función del protocolo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5547e-108">Valid combinations vary depending on the protocol selected.</span></span> <span data-ttu-id="5547e-109">Vea los temas enumerados abajo para obtener ejemplos de combinaciones válidas.</span><span class="sxs-lookup"><span data-stu-id="5547e-109">See the topics listed below for examples of valid combinations.</span></span>  
  
 <span data-ttu-id="5547e-110">**Nombre de alias**</span><span class="sxs-lookup"><span data-stu-id="5547e-110">**Alias Name**</span></span>  
 <span data-ttu-id="5547e-111">Nombre (alias) que desee usar para hacer referencia a esta conexión.</span><span class="sxs-lookup"><span data-stu-id="5547e-111">The name (alias) that you want to use to refer to this connection.</span></span>  
  
 <span data-ttu-id="5547e-112">**Nombre de canalización** / **Número de puerto**</span><span class="sxs-lookup"><span data-stu-id="5547e-112">**Pipe Name** / **Port No**</span></span>  
 <span data-ttu-id="5547e-113">Elementos adicionales de la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="5547e-113">Additional elements of the connection string.</span></span> <span data-ttu-id="5547e-114">El nombre de este cuadro varía según el protocolo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5547e-114">The name of this box varies with the selected protocol.</span></span>  
  
 <span data-ttu-id="5547e-115">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="5547e-115">**Protocol**</span></span>  
 <span data-ttu-id="5547e-116">Protocolo utilizado para la conexión.</span><span class="sxs-lookup"><span data-stu-id="5547e-116">The protocol used for the connection.</span></span>  
  
 <span data-ttu-id="5547e-117">**Server**</span><span class="sxs-lookup"><span data-stu-id="5547e-117">**Server**</span></span>  
 <span data-ttu-id="5547e-118">Nombre de la instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a la que se va a conectar.</span><span class="sxs-lookup"><span data-stu-id="5547e-118">The name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance being connected to.</span></span>  
  
## <a name="when-to-use-an-alias"></a><span data-ttu-id="5547e-119">Cuándo utilizar un alias</span><span class="sxs-lookup"><span data-stu-id="5547e-119">When to Use an Alias</span></span>  
 <span data-ttu-id="5547e-120">De forma predeterminada, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se conecta a una instancia local de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante el protocolo **Memoria compartida** y a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en otro equipo mediante **TCP/IP** o **Canalizaciones con nombre**.</span><span class="sxs-lookup"><span data-stu-id="5547e-120">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connects to a local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the **Shared Memory** protocol, and to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on another computer using either **TCP/IP** or **Named Pipes**.</span></span> <span data-ttu-id="5547e-121">Cree un alias cuando use TCP/IP o canalizaciones con nombre y desee proporcionar una cadena de conexión personalizada; o bien, cuando desee usar un nombre distinto del nombre de servidor para la conexión.</span><span class="sxs-lookup"><span data-stu-id="5547e-121">Create an alias when you are using TCP/IP or named pipes, and you want to provide a customized connection string, or when you want to use a name other than the server name for the connection.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="5547e-122">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5547e-122">Examples</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5547e-123">no escucha en el puerto TCP/IP predeterminado 1433, por lo que querrá proporcionar una cadena de conexión con otro número de puerto.</span><span class="sxs-lookup"><span data-stu-id="5547e-123">is not listening on the default TCP/IP port of 1433 so you want to provide a connection string with a different port number.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5547e-124">no escucha en la canalización con nombre predeterminada, por lo que desea proporcionar una cadena de conexión con una canalización con nombre diferente.</span><span class="sxs-lookup"><span data-stu-id="5547e-124">is not listening on the default named pipe so you want to provide a connection string with a different pipe name.</span></span>  
  
-   <span data-ttu-id="5547e-125">Una aplicación espera conectarse a una base de datos en el servidor llamado `ACCT`, pero la base de datos se ha consolidado como una instancia con el nombre `ACCT` en un servidor llamado `CENTRAL`.</span><span class="sxs-lookup"><span data-stu-id="5547e-125">An application expects to connect to a database on the server named `ACCT`, but that database has been consolidated as an instance named `ACCT` on a server named `CENTRAL`.</span></span> <span data-ttu-id="5547e-126">La aplicación no se puede modificar de forma sencilla.</span><span class="sxs-lookup"><span data-stu-id="5547e-126">The application cannot easily be changed.</span></span> <span data-ttu-id="5547e-127">Cree un alias llamado `ACCT`, con una cadena de conexión que apunte a `CENTRAL\ACCT`.</span><span class="sxs-lookup"><span data-stu-id="5547e-127">Create an alias named `ACCT`, with a connection string pointing to `CENTRAL\ACCT`.</span></span>  
  
## <a name="creating-a-valid-connection-string"></a><span data-ttu-id="5547e-128">Crear una cadena de conexión válida</span><span class="sxs-lookup"><span data-stu-id="5547e-128">Creating a Valid Connection String</span></span>  
 <span data-ttu-id="5547e-129">Vea los siguientes temas para obtener una descripción y ejemplos de combinaciones válidas de propiedades de alias:</span><span class="sxs-lookup"><span data-stu-id="5547e-129">See the following topics for a description and examples of valid combinations of alias properties:</span></span>  
  
-   [<span data-ttu-id="5547e-130">Crear una cadena de conexión válida con el protocolo de memoria compartida</span><span class="sxs-lookup"><span data-stu-id="5547e-130">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
-   [<span data-ttu-id="5547e-131">Crear una cadena de conexión válida con TCP/IP</span><span class="sxs-lookup"><span data-stu-id="5547e-131">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
-   [<span data-ttu-id="5547e-132">Crear una cadena de conexión válida con canalizaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="5547e-132">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
