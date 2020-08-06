---
title: Conexión a Microsoft SQL Server Analysis Services (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlserveras.f1
ms.assetid: 7f3244ee-b690-471c-893d-68e361c2d416
author: minewiskan
ms.author: owend
ms.openlocfilehash: 984979480e3ea54c86c986fa6dd9771aaf879cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669993"
---
# <a name="connect-to-microsoft-sql-server-analysis-services-ssas"></a><span data-ttu-id="cd73d-102">Conectarse a Microsoft SQL Server Analysis Services (SSAS)</span><span class="sxs-lookup"><span data-stu-id="cd73d-102">Connect to Microsoft SQL Server Analysis Services (SSAS)</span></span>
  <span data-ttu-id="cd73d-103">Esta página del **Asistente para la importación de tablas** le permite especificar valores para importar datos de un cubo de Microsoft SQL Server Analysis Services o un libro PowerPivot que se hospeda en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cd73d-103">This page of the **Table Import Wizard** enables you to specify settings to import data from a Microsoft SQL Server Analysis Services cube or a PowerPivot workbook that is hosted on SharePoint.</span></span> <span data-ttu-id="cd73d-104">Para tener acceso al asistente desde [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el menú **Modelo** , haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="cd73d-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="cd73d-105">Para conectarse a un origen de datos, debe tener instalado en el equipo el proveedor adecuado.</span><span class="sxs-lookup"><span data-stu-id="cd73d-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd73d-106">Las credenciales del usuario actual se utilizan al seleccionar una base de datos en esta página.</span><span class="sxs-lookup"><span data-stu-id="cd73d-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="cd73d-107">Sin embargo, la importación no se realizará correctamente si el usuario especificado en la página Información de suplantación no tiene privilegios suficientes para leer la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cd73d-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="cd73d-108">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="cd73d-108">UI element list</span></span>  
 <span data-ttu-id="cd73d-109">**Nombre descriptivo de la conexión**</span><span class="sxs-lookup"><span data-stu-id="cd73d-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="cd73d-110">Escriba un nombre único para esta conexión de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="cd73d-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="cd73d-111">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="cd73d-111">This is a required field.</span></span>  
  
 <span data-ttu-id="cd73d-112">**Nombre de servidor o de archivo**</span><span class="sxs-lookup"><span data-stu-id="cd73d-112">**Server or File Name**</span></span>  
 <span data-ttu-id="cd73d-113">Escriba uno de los datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd73d-113">Enter one of the following:</span></span>  
  
-   <span data-ttu-id="cd73d-114">Escriba el nombre o dirección IP del servidor SQL Server Analysis Services al que conectarse.</span><span class="sxs-lookup"><span data-stu-id="cd73d-114">Type the name or IP address of the SQL Server Analysis Services server to connect to.</span></span>  
  
     <span data-ttu-id="cd73d-115">Puede utilizar un punto (.), (local) o localhost para indicar el servidor local.</span><span class="sxs-lookup"><span data-stu-id="cd73d-115">You can use a period (.), (local), or localhost to indicate the local server.</span></span>  
  
-   <span data-ttu-id="cd73d-116">Escriba la dirección URL de un libro PowerPivot publicado en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cd73d-116">Type the URL of a PowerPivot workbook that is published to SharePoint.</span></span>  
  
 <span data-ttu-id="cd73d-117">**Utilizar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="cd73d-117">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="cd73d-118">Especifique si se utiliza la autenticación de Windows para conectarse a un servidor de SQL Server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="cd73d-118">Specify whether Windows Authentication is used to connect to a SQL Server Analysis Services server.</span></span>  
  
 <span data-ttu-id="cd73d-119">El modo de autenticación de Windows permite que un usuario pueda conectarse a través de una cuenta de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="cd73d-119">Windows Authentication mode enables a user to connect through a Windows user account.</span></span> <span data-ttu-id="cd73d-120">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="cd73d-120">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="cd73d-121">Cuando se utiliza la autenticación de Windows, las credenciales del usuario actual se utilizan al obtener una vista previa y filtrar datos en la ventana Propiedades de la tabla y en el Asistente para la importación.</span><span class="sxs-lookup"><span data-stu-id="cd73d-121">When Windows Authentication is used, the credentials of the current user are used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="cd73d-122">Estas credenciales no se utilizan para importar ni actualizar datos, sino que se utilizan las credenciales de Windows especificadas en la página Información de suplantación.</span><span class="sxs-lookup"><span data-stu-id="cd73d-122">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="cd73d-123">**Utilizar autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="cd73d-123">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="cd73d-124">Especifique si se utiliza la autenticación de SQL Server para conectarse a un servidor de SQL Server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="cd73d-124">Specify whether SQL Server Authentication is used to connect to a SQL Server Analysis Services server.</span></span>  
  
 <span data-ttu-id="cd73d-125">Con la autenticación de SQL Server, SQL Server realiza la autenticación por sí mismo comprobando si se ha configurado una cuenta de inicio de sesión de SQL Server y si la contraseña especificada coincide con la registrada previamente.</span><span class="sxs-lookup"><span data-stu-id="cd73d-125">With SQL Server Authentication, SQL Server performs the authentication itself by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span>  
  
 <span data-ttu-id="cd73d-126">La autenticación de SQL Server se utiliza para crear la cadena de conexión para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="cd73d-126">SQL Server Authentication is used to construct the connection string for the data source.</span></span> <span data-ttu-id="cd73d-127">Estas credenciales también se utilizan al obtener una vista previa y filtrar datos en la ventana Propiedades de la tabla y en el Asistente para la importación.</span><span class="sxs-lookup"><span data-stu-id="cd73d-127">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="cd73d-128">Estas credenciales no se utilizan para importar ni actualizar datos, sino que se utilizan las credenciales de Windows especificadas en la página Información de suplantación.</span><span class="sxs-lookup"><span data-stu-id="cd73d-128">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="cd73d-129">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="cd73d-129">**User name**</span></span>  
 <span data-ttu-id="cd73d-130">Especifique un nombre de usuario para la conexión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cd73d-130">Specify a user name for the database connection.</span></span> <span data-ttu-id="cd73d-131">Esta opción solo está disponible si ha seleccionado la autenticación de Windows para conectarse.</span><span class="sxs-lookup"><span data-stu-id="cd73d-131">This option is only available if you have selected to connect using Windows Authentication.</span></span>  
  
 <span data-ttu-id="cd73d-132">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="cd73d-132">**Password**</span></span>  
 <span data-ttu-id="cd73d-133">Especifique una contraseña para la conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cd73d-133">Specify a password for the database connection.</span></span> <span data-ttu-id="cd73d-134">Esta opción solo es modificable si ha seleccionado la autenticación de SQL Server para conectarse.</span><span class="sxs-lookup"><span data-stu-id="cd73d-134">This option is only editable if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="cd73d-135">**Guardar mi contraseña**</span><span class="sxs-lookup"><span data-stu-id="cd73d-135">**Save my password**</span></span>  
 <span data-ttu-id="cd73d-136">Especifique si la contraseña que ha escrito en el cuadro **Contraseña** está almacenada.</span><span class="sxs-lookup"><span data-stu-id="cd73d-136">Specify whether the password you have entered in the **Password** box is stored.</span></span> <span data-ttu-id="cd73d-137">Esta opción solo está disponible si ha seleccionado la autenticación de SQL Server para conectarse.</span><span class="sxs-lookup"><span data-stu-id="cd73d-137">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="cd73d-138">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="cd73d-138">**Database name**</span></span>  
 <span data-ttu-id="cd73d-139">Seleccione una base de datos en la lista de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="cd73d-139">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="cd73d-140">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="cd73d-140">**Advanced**</span></span>  
 <span data-ttu-id="cd73d-141">Establezca las propiedades de conexión adicionales con el cuadro de diálogo **Establecer propiedades avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="cd73d-141">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="cd73d-142">Para obtener más información, vea [Establecer propiedades avanzadas &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="cd73d-142">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="cd73d-143">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="cd73d-143">**Test Connection**</span></span>  
 <span data-ttu-id="cd73d-144">Intente establecer una conexión con el origen de datos usando la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="cd73d-144">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="cd73d-145">Se muestra un mensaje que indica si la conexión es correcta.</span><span class="sxs-lookup"><span data-stu-id="cd73d-145">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
