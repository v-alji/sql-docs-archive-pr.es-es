---
title: 'Tarea 1: crear una base de conocimiento y dominios | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 7d74a60b-8933-4038-bcbb-4e9dcc4f70e9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce1b22e3d677e831a1d518dacc1267ad0e6be236
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745581"
---
# <a name="task-1-creating-a-knowledge-base-and-domains"></a><span data-ttu-id="32799-102">Tarea 1: Creación de una base de conocimiento y dominios</span><span class="sxs-lookup"><span data-stu-id="32799-102">Task 1: Creating a Knowledge Base and Domains</span></span>
  <span data-ttu-id="32799-103">En esta tarea, creará la base de conocimiento **proveedores** y creará dominios que se usarán para la limpieza de datos y los datos coincidentes para quitar duplicados.</span><span class="sxs-lookup"><span data-stu-id="32799-103">In this task, you create the **Suppliers** knowledge base and create domains that is used for cleansing data and matching data to remove duplicates.</span></span>  
  
1.  <span data-ttu-id="32799-104">Inicie **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="32799-104">Launch **Data Quality Client**.</span></span> <span data-ttu-id="32799-105">Haga clic en **Inicio**, seleccione **todos los programas**, haga clic en **Microsoft SQL Server 2012**, en **Data Quality Services**y, a continuación, haga clic en **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="32799-105">Click **Start**, point to **All Programs**, click **Microsoft SQL Server 2012**, click **Data Quality Services**, and then click **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="32799-106">En el cuadro de diálogo **conectar al servidor** , seleccione la instancia del servidor de bases de datos en la que está instalado DQS y haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="32799-106">In the **Connect to Server** dialog box, select the database server instance on which the DQS is installed, and click **Connect**.</span></span>  
  
     <span data-ttu-id="32799-107">![Cuadro de diálogo conectar al servidor](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-01.jpg "Cuadro de diálogo Conectar a servidor")</span><span class="sxs-lookup"><span data-stu-id="32799-107">![Connect to Server Dialog Box](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-01.jpg "Connect to Server Dialog Box")</span></span>  
  
3.  <span data-ttu-id="32799-108">En la Página principal de Data Quality Client, en el panel administración de la **base de conocimiento** , haga clic en **nueva base de conocimiento**.</span><span class="sxs-lookup"><span data-stu-id="32799-108">In the Data Quality Client home page, in the **Knowledge Base Management** pane, click **New Knowledge Base**.</span></span>  
  
     <span data-ttu-id="32799-109">![Administración de bases de conocimiento - Nueva Knowledge Base](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-02.jpg "Administración de bases de conocimiento - Nueva Knowledge Base")</span><span class="sxs-lookup"><span data-stu-id="32799-109">![Knowledge Base Management - New KB](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-02.jpg "Knowledge Base Management - New KB")</span></span>  
  
4.  <span data-ttu-id="32799-110">Escriba **proveedores** como **nombre** de la base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="32799-110">Enter **Suppliers** for **Name** of the knowledge base.</span></span>  
  
     <span data-ttu-id="32799-111">![Nueva Knowledge Base - Administración de dominios](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-03.jpg "Nueva Knowledge Base - Administración de dominios")</span><span class="sxs-lookup"><span data-stu-id="32799-111">![New Knowledge Base - Domain Management](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-03.jpg "New Knowledge Base - Domain Management")</span></span>  
  
5.  <span data-ttu-id="32799-112">Confirme que el campo **crear base de conocimiento a partir de** está establecido en **ninguno** , ya que está creando la base de conocimiento **proveedores** desde cero.</span><span class="sxs-lookup"><span data-stu-id="32799-112">Confirm that **Create Knowledge Base from** field is set to **None** since you are creating the **Suppliers** knowledge base from scratch.</span></span>  
  
6.  <span data-ttu-id="32799-113">Confirme que está seleccionada la opción **Administración de dominios** para la **actividad** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="32799-113">Confirm that **Domain Management** is selected for the **Activity** and click **Next**.</span></span> <span data-ttu-id="32799-114">La actividad Administración de dominios permite crear y administrar dominios en la base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="32799-114">The Domain Management activity lets you create and manage domains in the knowledge base.</span></span>  
  
7.  <span data-ttu-id="32799-115">En la ventana **Administración de dominios** , haga clic en el botón **crear un dominio** de la barra de herramientas para crear un dominio.</span><span class="sxs-lookup"><span data-stu-id="32799-115">In the **Domain Management** window, click **Create a domain** toolbar button to create a domain.</span></span>  
  
     <span data-ttu-id="32799-116">![Botón de la barra de herramientas Crear dominio](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-04.jpg "Botón de la barra de herramientas Crear dominio")</span><span class="sxs-lookup"><span data-stu-id="32799-116">![Create Domain Toolbar Button](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-04.jpg "Create Domain Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="32799-117">En el cuadro de diálogo **crear dominio** , escriba **ID. de proveedor** para el **nombre de dominio**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="32799-117">In the **Create Domain** dialog box, type **Supplier ID** for the **Domain Name**, and click **OK**.</span></span>  
  
     <span data-ttu-id="32799-118">![Cuadro de diálogo Crear dominio](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-05.jpg "Cuadro de diálogo Crear dominio")</span><span class="sxs-lookup"><span data-stu-id="32799-118">![Create Domain Dialog Box](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-05.jpg "Create Domain Dialog Box")</span></span>  
  
9. <span data-ttu-id="32799-119">Repita el paso anterior para crear los dominios siguientes con toda la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="32799-119">Repeat previous step to create the following domains with all the default settings.</span></span> <span data-ttu-id="32799-120">Para simplificar el tutorial, establezca el **tipo de datos** de todos los dominios como **cadena**.</span><span class="sxs-lookup"><span data-stu-id="32799-120">To keep the tutorial simple, you set the **Data Type** of all the domains as **String**.</span></span> <span data-ttu-id="32799-121">Los otros tipos de datos permitidos son: Integer, Decimal y Date.</span><span class="sxs-lookup"><span data-stu-id="32799-121">The other allowed data types are: Integer, Decimal, and Date.</span></span> <span data-ttu-id="32799-122">Cuando se selecciona la opción **usar valores iniciales** (valor predeterminado), todos los sinónimos se reemplazan por el valor inicial del grupo de sinónimos en la salida.</span><span class="sxs-lookup"><span data-stu-id="32799-122">When the **Use Leading Values** option is selected (default), all synonyms are replaced with the leading value of the synonym group in the output.</span></span> <span data-ttu-id="32799-123">Al establecer la opción **normalizar cadena** (valor predeterminado), se quitan los caracteres especiales de los valores de dominio.</span><span class="sxs-lookup"><span data-stu-id="32799-123">Setting **Normalize String** option (default) removes any special characters in the domain values.</span></span> <span data-ttu-id="32799-124">La opción **dar formato a la salida para** permite seleccionar el formato que se aplica cuando se generan los valores de datos en el dominio.</span><span class="sxs-lookup"><span data-stu-id="32799-124">The **Format Output to** option lets you select the formatting that is applied when the data values in the domain are output.</span></span> <span data-ttu-id="32799-125">Seleccione **Habilitar corrector ortográfico** (predeterminado) para ejecutar el corrector ortográfico en todos los valores de cadena al rellenar el dominio.</span><span class="sxs-lookup"><span data-stu-id="32799-125">Select **Enable Speller** (default) to run Speller on all string values when populating the domain.</span></span> <span data-ttu-id="32799-126">La configuración de **idioma** especifica la versión de idioma del **corrector ortográfico** que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="32799-126">The **Language** setting specifies which language version of the **Speller** you want to apply.</span></span> <span data-ttu-id="32799-127">Seleccione **deshabilitar algoritmos de error de sintaxis** para rellenar el dominio sin comprobar si hay errores de sintaxis en los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="32799-127">Select **Disable Syntax Error Algorithms** to populate the domain without checking string values for syntax errors.</span></span> <span data-ttu-id="32799-128">Vea el tema sobre cómo [crear un dominio](https://msdn.microsoft.com/library/hh510401.aspx) en MSDN Library para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="32799-128">See [Create a Domain](https://msdn.microsoft.com/library/hh510401.aspx) topic in the MSDN library for more details.</span></span>  
  
    -   <span data-ttu-id="32799-129">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="32799-129">Supplier Name</span></span>  
  
    -   <span data-ttu-id="32799-130">Dirección de correo electrónico de contacto</span><span class="sxs-lookup"><span data-stu-id="32799-130">Contact Email</span></span>  
  
    -   <span data-ttu-id="32799-131">Address Line</span><span class="sxs-lookup"><span data-stu-id="32799-131">Address Line</span></span>  
  
    -   <span data-ttu-id="32799-132">City</span><span class="sxs-lookup"><span data-stu-id="32799-132">City</span></span>  
  
    -   <span data-ttu-id="32799-133">State</span><span class="sxs-lookup"><span data-stu-id="32799-133">State</span></span>  
  
    -   <span data-ttu-id="32799-134">Country</span><span class="sxs-lookup"><span data-stu-id="32799-134">Country</span></span>  
  
    -   <span data-ttu-id="32799-135">Zip</span><span class="sxs-lookup"><span data-stu-id="32799-135">Zip</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="32799-136">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="32799-136">Next Step</span></span>  
 [<span data-ttu-id="32799-137">Tarea 2: Adición manual de valores de dominio</span><span class="sxs-lookup"><span data-stu-id="32799-137">Task 2: Adding Domain Values Manually</span></span>](../../2014/tutorials/task-2-adding-domain-values-manually.md)  
  
  
