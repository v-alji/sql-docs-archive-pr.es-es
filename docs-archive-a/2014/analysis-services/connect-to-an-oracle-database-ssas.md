---
title: Conexión a un Oracle Database (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connoracledb.f1
ms.assetid: 9bd177fb-8539-46cd-bf96-189ade52c2a1
author: minewiskan
ms.author: owend
ms.openlocfilehash: b0260983f5060ecba7f618975e805ff63c507d5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669997"
---
# <a name="connect-to-an-oracle-database-ssas"></a><span data-ttu-id="7d2fc-102">Conectarse a una base de datos de Oracle (SSAS)</span><span class="sxs-lookup"><span data-stu-id="7d2fc-102">Connect to an Oracle Database (SSAS)</span></span>
  <span data-ttu-id="7d2fc-103">Esta página del **Asistente para la importación de tablas** le permite especificar los valores para conectarse con una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-103">This page of the **Table Import Wizard** enables you to specify settings to connect to an Oracle database.</span></span> <span data-ttu-id="7d2fc-104">Para tener acceso al asistente desde [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el menú **Modelo** , haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="7d2fc-105">Para conectarse a un origen de datos, debe tener instalado en el equipo el proveedor adecuado.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d2fc-106">Las credenciales del usuario actual se utilizan al seleccionar una base de datos en esta página.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="7d2fc-107">Sin embargo, la importación no se realizará correctamente si el usuario especificado en la página Información de suplantación no tiene privilegios suficientes para leer la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="7d2fc-108">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="7d2fc-108">UI element list</span></span>  
 <span data-ttu-id="7d2fc-109">**Nombre descriptivo de la conexión**</span><span class="sxs-lookup"><span data-stu-id="7d2fc-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="7d2fc-110">Escriba un nombre único para esta conexión de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="7d2fc-111">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-111">This is a required field.</span></span>  
  
 <span data-ttu-id="7d2fc-112">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="7d2fc-112">**Server name**</span></span>  
 <span data-ttu-id="7d2fc-113">Escriba o seleccione el nombre de la instancia de servidor a la que va a conectarse.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-113">Type or select the name of the server instance to connect to.</span></span>  
  
 <span data-ttu-id="7d2fc-114">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="7d2fc-114">**User name**</span></span>  
 <span data-ttu-id="7d2fc-115">Especifique un nombre de usuario para la conexión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="7d2fc-116">Este nombre de usuario se utiliza para crear la cadena de conexión para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="7d2fc-117">Estas credenciales también se utilizan al obtener una vista previa y filtrar datos en la ventana Propiedades de la tabla y en el Asistente para la importación.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="7d2fc-118">Estas credenciales no se utilizan para importar ni actualizar datos, sino que se utilizan las credenciales de Windows especificadas en la página Información de suplantación.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="7d2fc-119">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="7d2fc-119">**Password**</span></span>  
 <span data-ttu-id="7d2fc-120">Especifique una contraseña para la conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="7d2fc-121">**Guardar mi contraseña**</span><span class="sxs-lookup"><span data-stu-id="7d2fc-121">**Save my password**</span></span>  
 <span data-ttu-id="7d2fc-122">Especifique si la contraseña que ha escrito en el cuadro **Contraseña** está almacenada.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="7d2fc-123">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="7d2fc-123">**Advanced**</span></span>  
 <span data-ttu-id="7d2fc-124">Establezca las propiedades de conexión adicionales con el cuadro de diálogo **Establecer propiedades avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="7d2fc-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="7d2fc-125">Para obtener más información, vea [Establecer propiedades avanzadas &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="7d2fc-125">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="7d2fc-126">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="7d2fc-126">**Test Connection**</span></span>  
 <span data-ttu-id="7d2fc-127">Intente establecer una conexión con el origen de datos usando la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-127">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="7d2fc-128">Se muestra un mensaje que indica si la conexión es correcta.</span><span class="sxs-lookup"><span data-stu-id="7d2fc-128">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
