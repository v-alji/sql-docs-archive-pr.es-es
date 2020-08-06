---
title: Iniciar la utilidad sqlcmd
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 00d57437-7a29-4da1-b639-ee990db055fb
author: rothja
ms.author: jroth
ms.openlocfilehash: d71e6f140238599b3f22850ee9b63a0ee25d900b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669572"
---
# <a name="start-the-sqlcmd-utility"></a><span data-ttu-id="003a7-102">Iniciar la utilidad sqlcmd</span><span class="sxs-lookup"><span data-stu-id="003a7-102">Start the sqlcmd Utility</span></span>
  <span data-ttu-id="003a7-103">Para empezar a usar `sqlcmd`, primero debe iniciar la utilidad y conectarse a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="003a7-103">To begin using `sqlcmd`, you must first launch the utility and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="003a7-104">Puede conectarse a una instancia con nombre o a la instancia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="003a7-104">You can connect to either a default or named instance.</span></span> <span data-ttu-id="003a7-105">El primer paso consiste en iniciar la utilidad `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="003a7-105">The first step is to start the `sqlcmd` utility.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="003a7-106">La autenticación de Windows es el modo de autenticación predeterminado para `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="003a7-106">Windows Authentication is the default authentication mode for `sqlcmd`.</span></span> <span data-ttu-id="003a7-107">Para usar la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , debe especificar un nombre de usuario y una contraseña mediante las opciones **-U** y **-P** .</span><span class="sxs-lookup"><span data-stu-id="003a7-107">To use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must specify a user name and password by using the **-U** and **-P** options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="003a7-108"> De forma predeterminada, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] se instala como la instancia con nombre **sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="003a7-108">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs as the named instance **sqlexpress**.</span></span>  
  
 <span data-ttu-id="003a7-109">Si no se ha conectado antes a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], quizás tenga que configurar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que acepte conexiones.</span><span class="sxs-lookup"><span data-stu-id="003a7-109">If you have not connected to this instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] before, you may have to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
### <a name="to-start-the-sqlcmd-utility-and-connect-to-a-default-instance-of-sql-server"></a><span data-ttu-id="003a7-110">Para iniciar la utilidad sqlcmd y conectar con una instancia predeterminada de SQL Server</span><span class="sxs-lookup"><span data-stu-id="003a7-110">To start the sqlcmd utility and connect to a default instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="003a7-111">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="003a7-111">On the **Start** menu click **Run**.</span></span> <span data-ttu-id="003a7-112">En el cuadro **Abrir** , escriba **cmd**y, a continuación, haga clic en **Aceptar** para abrir una ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="003a7-112">In the **Open** box type **cmd**, and then click **OK** to open a Command Prompt window.</span></span>  
  
2.  <span data-ttu-id="003a7-113">En el símbolo del sistema, escriba `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="003a7-113">At the command prompt, type `sqlcmd`.</span></span>  
  
3.  <span data-ttu-id="003a7-114">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="003a7-114">Press ENTER.</span></span>  
  
     <span data-ttu-id="003a7-115">Ahora tiene una conexión de confianza con la instancia predeterminada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se está ejecutando en el equipo.</span><span class="sxs-lookup"><span data-stu-id="003a7-115">You now have a trusted connection to the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on your computer.</span></span>  
  
     <span data-ttu-id="003a7-116">**1>** es el `sqlcmd` símbolo del sistema que especifica el número de línea.</span><span class="sxs-lookup"><span data-stu-id="003a7-116">**1>** is the `sqlcmd` prompt that specifies the line number.</span></span> <span data-ttu-id="003a7-117">Cada vez que presione ENTRAR, el número se incrementará en uno.</span><span class="sxs-lookup"><span data-stu-id="003a7-117">Each time you press ENTER, the number increases by one.</span></span>  
  
4.  <span data-ttu-id="003a7-118">Para finalizar la `sqlcmd` sesión, escriba `EXIT` en el `sqlcmd` símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="003a7-118">To end the `sqlcmd` session, type `EXIT` at the `sqlcmd` prompt.</span></span>  
  
### <a name="to-start-the-sqlcmd-utility-and-connect-to-a-named-instance-of-sql-server"></a><span data-ttu-id="003a7-119">Para iniciar la utilidad sqlcmd y conectar con una instancia con nombre de SQL Server</span><span class="sxs-lookup"><span data-stu-id="003a7-119">To start the sqlcmd utility and connect to a named instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="003a7-120">Abra una ventana del símbolo del sistema y escriba `sqlcmd -S` *myServer\instanceName*.</span><span class="sxs-lookup"><span data-stu-id="003a7-120">Open a Command Prompt window, and type `sqlcmd -S`*myServer\instanceName*.</span></span> <span data-ttu-id="003a7-121">Reemplace *myServer\instanceName* por el nombre del equipo y la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a la que quiera conectarse.</span><span class="sxs-lookup"><span data-stu-id="003a7-121">Replace *myServer\instanceName* with the name of the computer and the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to connect to.</span></span>  
  
2.  <span data-ttu-id="003a7-122">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="003a7-122">Press ENTER.</span></span>  
  
     <span data-ttu-id="003a7-123">El `sqlcmd` símbolo del sistema (1>) indica que está conectado a la instancia especificada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="003a7-123">The `sqlcmd` prompt (1>) indicates that you are connected to the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="003a7-124">Las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] escritas están almacenadas en un búfer.</span><span class="sxs-lookup"><span data-stu-id="003a7-124">Entered [!INCLUDE[tsql](../../includes/tsql-md.md)] statements are stored in a buffer.</span></span> <span data-ttu-id="003a7-125">Se ejecutan como un lote cuando se encuentra el comando GO.</span><span class="sxs-lookup"><span data-stu-id="003a7-125">They are executed as a batch when the GO command is encountered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="003a7-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="003a7-126">See Also</span></span>  
 [<span data-ttu-id="003a7-127">Ejecutar archivos de scripts Transact-SQL mediante sqlcmd</span><span class="sxs-lookup"><span data-stu-id="003a7-127">Run Transact-SQL Script Files Using sqlcmd</span></span>](sqlcmd-run-transact-sql-script-files.md)  
  
  
