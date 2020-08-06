---
title: Conectarse a una base de datos de Microsoft SQL Server (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlserverdb.f1
ms.assetid: 6ebfe029-dbba-4f0d-a556-328e79ef629f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 64267cd65836cf8e6c8d8b26a177de595894b601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670016"
---
# <a name="connect-to-a-microsoft-sql-server-database-ssas"></a><span data-ttu-id="1cd52-102">Conectarse a una base de datos de Microsoft SQL Server (SSAS)</span><span class="sxs-lookup"><span data-stu-id="1cd52-102">Connect to a Microsoft SQL Server Database (SSAS)</span></span>
  <span data-ttu-id="1cd52-103">Esta página del **Asistente para la importación de tablas** le permite especificar los valores para conectarse con una base de datos de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1cd52-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft SQL Server database.</span></span> <span data-ttu-id="1cd52-104">Para tener acceso al asistente desde [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el menú **Modelo** , haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="1cd52-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="1cd52-105">Para conectarse a un origen de datos, debe tener instalado en el equipo el proveedor adecuado.</span><span class="sxs-lookup"><span data-stu-id="1cd52-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1cd52-106">Las credenciales del usuario actual se utilizan al seleccionar una base de datos en esta página.</span><span class="sxs-lookup"><span data-stu-id="1cd52-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="1cd52-107">Sin embargo, la importación no se realizará correctamente si el usuario especificado en la página Información de suplantación no tiene privilegios suficientes para leer la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1cd52-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="1cd52-108">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="1cd52-108">UI element list</span></span>  
 <span data-ttu-id="1cd52-109">**Nombre descriptivo de la conexión**</span><span class="sxs-lookup"><span data-stu-id="1cd52-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="1cd52-110">Escriba un nombre único para esta conexión de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1cd52-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="1cd52-111">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1cd52-111">This is a required field.</span></span>  
  
 <span data-ttu-id="1cd52-112">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="1cd52-112">**Server name**</span></span>  
 <span data-ttu-id="1cd52-113">Seleccione el nombre o escriba el nombre o la dirección IP de la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a la que conectarse.</span><span class="sxs-lookup"><span data-stu-id="1cd52-113">Select the name, or type the name or IP address, of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to connect to.</span></span>  
  
 <span data-ttu-id="1cd52-114">Puede utilizar un punto (.), (local) o localhost para indicar el servidor local.</span><span class="sxs-lookup"><span data-stu-id="1cd52-114">You can use a period (.), (local), or localhost to indicate the local server.</span></span>  
  
 <span data-ttu-id="1cd52-115">**Utilizar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="1cd52-115">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="1cd52-116">Especifique si la autenticación de Windows se usa para conectarse a una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cd52-116">Specify whether Windows Authentication is used to connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1cd52-117">El modo de autenticación de Windows permite que un usuario pueda conectarse a través de una cuenta de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="1cd52-117">Windows Authentication mode enables a user to connect by using a Windows user account.</span></span> <span data-ttu-id="1cd52-118">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="1cd52-118">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="1cd52-119">Cuando se utiliza la autenticación de Windows, las credenciales del usuario actual se utilizan al obtener una vista previa y filtrar datos en la ventana Propiedades de la tabla y en el Asistente para la importación.</span><span class="sxs-lookup"><span data-stu-id="1cd52-119">When Windows Authentication is used, the credentials of the current user are used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="1cd52-120">Estas credenciales no se utilizan para importar ni actualizar datos, sino que se utilizan las credenciales de Windows especificadas en la página Información de suplantación.</span><span class="sxs-lookup"><span data-stu-id="1cd52-120">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation information page are used instead.</span></span>  
  
 <span data-ttu-id="1cd52-121">**Utilizar autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="1cd52-121">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="1cd52-122">Especifique si la autenticación de SQL Server se usa para conectarse a una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cd52-122">Specify whether SQL Server Authentication is used to connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1cd52-123">Con la autenticación de SQL Server, SQL Server realiza la autenticación por sí mismo comprobando si se ha configurado una cuenta de inicio de sesión de SQL Server y si la contraseña especificada coincide con la registrada previamente.</span><span class="sxs-lookup"><span data-stu-id="1cd52-123">With SQL Server Authentication, SQL Server performs the authentication itself by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span>  
  
 <span data-ttu-id="1cd52-124">La autenticación de SQL Server se utiliza para crear la cadena de conexión para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1cd52-124">SQL Server Authentication is used to construct the connection string for the data source.</span></span> <span data-ttu-id="1cd52-125">Estas credenciales también se utilizan al obtener una vista previa y filtrar datos en la ventana Propiedades de la tabla y en el Asistente para la importación.</span><span class="sxs-lookup"><span data-stu-id="1cd52-125">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="1cd52-126">Estas credenciales no se utilizan para importar ni actualizar datos, sino que se utilizan las credenciales de Windows especificadas en la página Información de suplantación.</span><span class="sxs-lookup"><span data-stu-id="1cd52-126">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="1cd52-127">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="1cd52-127">**User name**</span></span>  
 <span data-ttu-id="1cd52-128">Especifique un nombre de usuario para la conexión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1cd52-128">Specify a user name for the database connection.</span></span> <span data-ttu-id="1cd52-129">Esta opción solo está disponible si ha seleccionado la autenticación de SQL Server para conectarse.</span><span class="sxs-lookup"><span data-stu-id="1cd52-129">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="1cd52-130">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="1cd52-130">**Password**</span></span>  
 <span data-ttu-id="1cd52-131">Especifique una contraseña para la conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1cd52-131">Specify a password for the database connection.</span></span> <span data-ttu-id="1cd52-132">Esta opción solo es modificable si ha seleccionado la autenticación de SQL Server para conectarse.</span><span class="sxs-lookup"><span data-stu-id="1cd52-132">This option is only editable if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="1cd52-133">**Guardar mi contraseña**</span><span class="sxs-lookup"><span data-stu-id="1cd52-133">**Save my password**</span></span>  
 <span data-ttu-id="1cd52-134">Especifique si la contraseña que ha escrito en el cuadro **Contraseña** está almacenada.</span><span class="sxs-lookup"><span data-stu-id="1cd52-134">Specify whether the password you have entered in the **Password** box is stored.</span></span> <span data-ttu-id="1cd52-135">Esta opción solo está disponible si ha seleccionado la autenticación de SQL Server para conectarse.</span><span class="sxs-lookup"><span data-stu-id="1cd52-135">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="1cd52-136">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="1cd52-136">**Database name**</span></span>  
 <span data-ttu-id="1cd52-137">Seleccione una base de datos en la lista de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="1cd52-137">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="1cd52-138">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="1cd52-138">**Advanced**</span></span>  
 <span data-ttu-id="1cd52-139">Establezca las propiedades de conexión adicionales con el cuadro de diálogo **Establecer propiedades avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="1cd52-139">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="1cd52-140">Para obtener más información, vea [Establecer propiedades avanzadas &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="1cd52-140">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="1cd52-141">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="1cd52-141">**Test Connection**</span></span>  
 <span data-ttu-id="1cd52-142">Intente establecer una conexión con el origen de datos usando la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="1cd52-142">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="1cd52-143">Se muestra un mensaje que indica si la conexión fue correcta.</span><span class="sxs-lookup"><span data-stu-id="1cd52-143">A message is displayed indicating whether the connection was successful.</span></span>  
  
  
