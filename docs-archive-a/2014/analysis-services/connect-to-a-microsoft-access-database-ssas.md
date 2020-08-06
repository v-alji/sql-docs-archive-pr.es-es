---
title: Conectarse a una base de datos de Microsoft Access (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connaccessdb.f1
ms.assetid: 9fa81839-dd8b-41d3-915e-c774a707ed53
author: minewiskan
ms.author: owend
ms.openlocfilehash: fbb180a754b6bc276d588997117eb84fd1a5a873
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670017"
---
# <a name="connect-to-a-microsoft-access-database-ssas"></a><span data-ttu-id="f8b2c-102">Conectarse a una base de datos de Microsoft Access (SSAS)</span><span class="sxs-lookup"><span data-stu-id="f8b2c-102">Connect to a Microsoft Access Database (SSAS)</span></span>
  <span data-ttu-id="f8b2c-103">Esta página del **Asistente para la importación de tablas** le permite especificar los valores para conectarse con una base de datos de Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="f8b2c-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft Access database.</span></span> <span data-ttu-id="f8b2c-104">Para tener acceso al asistente desde [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el menú **Modelo** , haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="f8b2c-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="f8b2c-105">Para conectarse a una base de datos de Microsoft Access, debe tener instalado en el equipo el proveedor ACE adecuado.</span><span class="sxs-lookup"><span data-stu-id="f8b2c-105">To connect to a Microsoft Access database, you must have the appropriate ACE provider installed on your computer.</span></span> <span data-ttu-id="f8b2c-106">Para más información, vea [Orígenes de datos compatibles &#40;SSAS tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="f8b2c-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f8b2c-107">Las credenciales del usuario actual se utilizan al seleccionar un archivo en esta página.</span><span class="sxs-lookup"><span data-stu-id="f8b2c-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="f8b2c-108">Sin embargo, la importación no se realizará correctamente si el usuario especificado en la página Información de suplantación no tiene privilegios suficientes para leer el archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f8b2c-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="f8b2c-109">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f8b2c-109">UI element list</span></span>  
 <span data-ttu-id="f8b2c-110">**Nombre descriptivo de la conexión**</span><span class="sxs-lookup"><span data-stu-id="f8b2c-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="f8b2c-111">Escriba un nombre único para esta conexión de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f8b2c-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="f8b2c-112">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f8b2c-112">This is a required field.</span></span>  
  
 <span data-ttu-id="f8b2c-113">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="f8b2c-113">**Database name**</span></span>  
 <span data-ttu-id="f8b2c-114">Especifique la ruta de acceso completa para un archivo de base de datos de Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="f8b2c-114">Specify the full path for a Microsoft Access database file.</span></span>  
  
 <span data-ttu-id="f8b2c-115">**Browse**</span><span class="sxs-lookup"><span data-stu-id="f8b2c-115">**Browse**</span></span>  
 <span data-ttu-id="f8b2c-116">Navegue a una ubicación donde haya un archivo de base de datos de Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="f8b2c-116">Navigate to a location where a Microsoft Access database file is available.</span></span>  
  
 <span data-ttu-id="f8b2c-117">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="f8b2c-117">**User name**</span></span>  
 <span data-ttu-id="f8b2c-118">Especifique un nombre de usuario para la conexión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f8b2c-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="f8b2c-119">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="f8b2c-119">**Password**</span></span>  
 <span data-ttu-id="f8b2c-120">Especifique una contraseña para la conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f8b2c-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="f8b2c-121">**Guardar mi contraseña**</span><span class="sxs-lookup"><span data-stu-id="f8b2c-121">**Save my password**</span></span>  
 <span data-ttu-id="f8b2c-122">Especifique si la contraseña que ha escrito en el cuadro **Contraseña** está almacenada.</span><span class="sxs-lookup"><span data-stu-id="f8b2c-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="f8b2c-123">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="f8b2c-123">**Advanced**</span></span>  
 <span data-ttu-id="f8b2c-124">Establezca las propiedades de conexión adicionales con el cuadro de diálogo **Establecer propiedades avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="f8b2c-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span>  
  
 <span data-ttu-id="f8b2c-125">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="f8b2c-125">**Test Connection**</span></span>  
 <span data-ttu-id="f8b2c-126">Intente establecer una conexión con el origen de datos usando la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="f8b2c-126">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="f8b2c-127">Se muestra un mensaje que indica si la conexión es correcta.</span><span class="sxs-lookup"><span data-stu-id="f8b2c-127">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
