---
title: Conexión a un Azure SQL Database (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlazure.f1
ms.assetid: 4e0344e9-1822-4698-ad22-05f1f341ced7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91ae6f0f5ab95d3013b6348bd43ddb746fff1c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670006"
---
# <a name="connect-to-an-azure-sql-database-ssas"></a><span data-ttu-id="d2058-102">Conexión con una Azure SQL Database (SSAS)</span><span class="sxs-lookup"><span data-stu-id="d2058-102">Connect to an Azure SQL Database (SSAS)</span></span>
  <span data-ttu-id="d2058-103">Esta página del **Asistente para la importación de tablas** le permite conectar con [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2058-103">This page of the **Table Import Wizard** enables you to connect to a [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)].</span></span> <span data-ttu-id="d2058-104">Para tener acceso al asistente desde [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el menú **Modelo** , haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="d2058-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2058-105">Si va a conectarse a un conjunto de datos de Azure DataMarket, vea [Conectarse a un informe o a una fuente de distribución de datos &#40;SSAS&#41;](connect-to-a-report-or-data-feed-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="d2058-105">If you are connecting to an Azure DataMarket dataset, see [Connect to a Report or Data Feed &#40;SSAS&#41;](connect-to-a-report-or-data-feed-ssas.md).</span></span>  
  
 <span data-ttu-id="d2058-106">[!INCLUDE[ssSDS](../includes/sssds-md.md)] es una base de datos relacional hospedada con la que se conecta usando la autenticación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d2058-106">The [!INCLUDE[ssSDS](../includes/sssds-md.md)] is a hosted, relational database that you connect to by using SQL Server Authentication.</span></span> <span data-ttu-id="d2058-107">Para obtener más información sobre [!INCLUDE[ssSDS](../includes/sssds-md.md)], vea el sitio web [Base de datos SQL](https://go.microsoft.com/fwlink/?LinkID=157856).</span><span class="sxs-lookup"><span data-stu-id="d2058-107">For more information about [!INCLUDE[ssSDS](../includes/sssds-md.md)], see the web site [SQL Database](https://go.microsoft.com/fwlink/?LinkID=157856).</span></span> <span data-ttu-id="d2058-108">Para conectarse a un origen de datos, debe tener instalado en el equipo el proveedor adecuado.</span><span class="sxs-lookup"><span data-stu-id="d2058-108">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2058-109">Las credenciales del usuario actual se utilizan al seleccionar una base de datos en esta página.</span><span class="sxs-lookup"><span data-stu-id="d2058-109">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="d2058-110">Sin embargo, la importación no se realizará correctamente si el usuario especificado en la página Información de suplantación no tiene privilegios suficientes para leer la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2058-110">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="d2058-111">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="d2058-111">UI element list</span></span>  
 <span data-ttu-id="d2058-112">**Nombre descriptivo de la conexión**</span><span class="sxs-lookup"><span data-stu-id="d2058-112">**Friendly connection name**</span></span>  
 <span data-ttu-id="d2058-113">Escriba un nombre único para esta conexión de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d2058-113">Type a unique name for this data source connection.</span></span> <span data-ttu-id="d2058-114">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d2058-114">This is a required field.</span></span>  
  
 <span data-ttu-id="d2058-115">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="d2058-115">**Server name**</span></span>  
 <span data-ttu-id="d2058-116">Escriba el nombre o la dirección IP del servidor al que va a conectarse.</span><span class="sxs-lookup"><span data-stu-id="d2058-116">Type the name, or IP address, of the server to connect to.</span></span>  
  
 <span data-ttu-id="d2058-117">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="d2058-117">**User name**</span></span>  
 <span data-ttu-id="d2058-118">Especifique un nombre de usuario para la conexión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d2058-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="d2058-119">Este nombre de usuario se utiliza para crear la cadena de conexión para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d2058-119">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="d2058-120">Estas credenciales también se utilizan al obtener una vista previa y filtrar datos en la ventana Propiedades de la tabla y en el Asistente para la importación.</span><span class="sxs-lookup"><span data-stu-id="d2058-120">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="d2058-121">Estas credenciales no se utilizan para importar ni actualizar datos, sino que se utilizan las credenciales de Windows especificadas en la página Información de suplantación.</span><span class="sxs-lookup"><span data-stu-id="d2058-121">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="d2058-122">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="d2058-122">**Password**</span></span>  
 <span data-ttu-id="d2058-123">Especifique una contraseña para la conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d2058-123">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="d2058-124">**Guardar mi contraseña**</span><span class="sxs-lookup"><span data-stu-id="d2058-124">**Save my password**</span></span>  
 <span data-ttu-id="d2058-125">Especifique si la contraseña que ha escrito en el cuadro **Contraseña** está almacenada.</span><span class="sxs-lookup"><span data-stu-id="d2058-125">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="d2058-126">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="d2058-126">**Database name**</span></span>  
 <span data-ttu-id="d2058-127">Seleccione una base de datos en la lista de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="d2058-127">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="d2058-128">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="d2058-128">**Advanced**</span></span>  
 <span data-ttu-id="d2058-129">Establezca las propiedades de conexión adicionales con el cuadro de diálogo **Establecer propiedades avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="d2058-129">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="d2058-130">Para obtener más información, vea [Establecer propiedades avanzadas &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="d2058-130">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="d2058-131">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="d2058-131">**Test Connection**</span></span>  
 <span data-ttu-id="d2058-132">Intente establecer una conexión con el origen de datos usando la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="d2058-132">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="d2058-133">Se muestra un mensaje que indica si la conexión es correcta.</span><span class="sxs-lookup"><span data-stu-id="d2058-133">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
