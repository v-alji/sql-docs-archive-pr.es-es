---
title: Conectarse a una base de datos DB2 (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conndb2db.f1
ms.assetid: eeef3697-a4fd-4263-ba7e-f86afa1f46cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: f36a583956c1fe75bb0a6acd827d083a6c7562f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670022"
---
# <a name="connect-to-a-db2-database-ssas"></a><span data-ttu-id="185df-102">Conectarse a una base de datos de DB2 (SSAS)</span><span class="sxs-lookup"><span data-stu-id="185df-102">Connect to a DB2 Database (SSAS)</span></span>
  <span data-ttu-id="185df-103">Esta página del **Asistente para la importación de tablas** le permite especificar los valores para conectarse con una base de datos de DB2.</span><span class="sxs-lookup"><span data-stu-id="185df-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a DB2 database.</span></span> <span data-ttu-id="185df-104">Para tener acceso al asistente desde [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el menú **Modelo** , haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="185df-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="185df-105">Para conectarse a un origen de datos, debe tener instalado en el equipo el proveedor adecuado.</span><span class="sxs-lookup"><span data-stu-id="185df-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="185df-106">Al seleccionar una base de datos en esta página, se usan las credenciales del usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="185df-106">When selecting a database in this page, the credentials of the user specified are used.</span></span> <span data-ttu-id="185df-107">Sin embargo, la importación no se realizará correctamente si el usuario especificado en la página Información de suplantación no tiene privilegios suficientes para leer la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="185df-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="185df-108">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="185df-108">UI element list</span></span>  
 <span data-ttu-id="185df-109">**Nombre descriptivo de la conexión**</span><span class="sxs-lookup"><span data-stu-id="185df-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="185df-110">Escriba un nombre único para esta conexión de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="185df-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="185df-111">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="185df-111">This is a required field.</span></span>  
  
 <span data-ttu-id="185df-112">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="185df-112">**Server name**</span></span>  
 <span data-ttu-id="185df-113">Escriba o seleccione la instancia de servidor a la que va a conectarse.</span><span class="sxs-lookup"><span data-stu-id="185df-113">Type or select the server instance to connect to.</span></span>  
  
 <span data-ttu-id="185df-114">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="185df-114">**User name**</span></span>  
 <span data-ttu-id="185df-115">Especifique un nombre de usuario para la conexión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="185df-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="185df-116">Este nombre de usuario se utiliza para crear la cadena de conexión para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="185df-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="185df-117">Estas credenciales también se utilizan al obtener una vista previa y filtrar datos en la ventana Propiedades de la tabla y en el Asistente para la importación.</span><span class="sxs-lookup"><span data-stu-id="185df-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="185df-118">Estas credenciales no se utilizan para importar ni actualizar datos, sino que se utilizan las credenciales de Windows especificadas en la página Información de suplantación.</span><span class="sxs-lookup"><span data-stu-id="185df-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="185df-119">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="185df-119">**Password**</span></span>  
 <span data-ttu-id="185df-120">Especifique una contraseña para la conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="185df-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="185df-121">**Guardar mi contraseña**</span><span class="sxs-lookup"><span data-stu-id="185df-121">**Save my password**</span></span>  
 <span data-ttu-id="185df-122">Especifique si la contraseña que ha escrito en el cuadro **Contraseña** está almacenada.</span><span class="sxs-lookup"><span data-stu-id="185df-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="185df-123">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="185df-123">**Database name**</span></span>  
 <span data-ttu-id="185df-124">Seleccione una base de datos en la lista de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="185df-124">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="185df-125">**Colección de paquetes**</span><span class="sxs-lookup"><span data-stu-id="185df-125">**Package Collection**</span></span>  
 <span data-ttu-id="185df-126">Especifique el nombre de la recolección para los paquetes de DB2.</span><span class="sxs-lookup"><span data-stu-id="185df-126">Specify the name of the collection for the DB2 packages.</span></span> <span data-ttu-id="185df-127">Un proveedor utiliza los paquetes para emitir instrucciones SQL y llamar a procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="185df-127">A provider uses packages to issue SQL statements and call stored procedures.</span></span>  
  
 <span data-ttu-id="185df-128">**Esquema predeterminado**</span><span class="sxs-lookup"><span data-stu-id="185df-128">**Default Schema**</span></span>  
 <span data-ttu-id="185df-129">Especifique el nombre del esquema predeterminado para la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="185df-129">Specify the name of the default schema for the selected database.</span></span>  
  
 <span data-ttu-id="185df-130">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="185df-130">**Advanced**</span></span>  
 <span data-ttu-id="185df-131">Establezca las propiedades de conexión adicionales mediante el cuadro de diálogo **establecer propiedades avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="185df-131">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="185df-132">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="185df-132">**Test Connection**</span></span>  
 <span data-ttu-id="185df-133">Intente establecer una conexión con el origen de datos usando la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="185df-133">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="185df-134">Se muestra un mensaje que indica si la conexión es correcta.</span><span class="sxs-lookup"><span data-stu-id="185df-134">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
