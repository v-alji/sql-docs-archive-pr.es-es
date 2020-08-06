---
title: 'Paso 7: Agregar y configurar el destino de OLE DB | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 442c841d-d528-4bf0-8724-7156f909ee50
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da917ccc4ca756c2442e70477976b5a71f7eb56e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673120"
---
# <a name="step-7-adding-and-configuring-the-ole-db-destination"></a><span data-ttu-id="8c92f-102">Paso 7: Adición y configuración del destino de OLE DB</span><span class="sxs-lookup"><span data-stu-id="8c92f-102">Step 7: Adding and Configuring the OLE DB Destination</span></span>
  <span data-ttu-id="8c92f-103">Ahora, el paquete puede extraer datos de un origen de archivo plano y transformar dichos datos en un formato compatible con el destino.</span><span class="sxs-lookup"><span data-stu-id="8c92f-103">Your package now can extract data from the flat file source and transform that data into a format that is compatible with the destination.</span></span> <span data-ttu-id="8c92f-104">La tarea siguiente consiste realmente en cargar los datos transformados en el destino.</span><span class="sxs-lookup"><span data-stu-id="8c92f-104">The next task is to actually load the transformed data into the destination.</span></span> <span data-ttu-id="8c92f-105">Para cargar los datos, debe agregar un destino de OLE DB al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="8c92f-105">To load the data, you must add an OLE DB destination to the data flow.</span></span> <span data-ttu-id="8c92f-106">El destino de OLE DB puede utilizar una tabla de bases de datos, una vista o un comando SQL para cargar datos en distintas bases de datos compatibles con OLE DB.</span><span class="sxs-lookup"><span data-stu-id="8c92f-106">The OLE DB destination can use a database table, view, or an SQL command to load data into a variety of OLE DB-compliant databases.</span></span>  
  
 <span data-ttu-id="8c92f-107">En este procedimiento, se agrega y configura un destino de OLE DB para utilizar el administrador de conexiones de OLE DB creado con anterioridad.</span><span class="sxs-lookup"><span data-stu-id="8c92f-107">In this procedure, you add and configure an OLE DB destination to use the OLE DB connection manager that you previously created.</span></span>  
  
### <a name="to-add-and-configure-the-sample-ole-db-destination"></a><span data-ttu-id="8c92f-108">Para agregar y configurar un destino de OLE DB de ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c92f-108">To add and configure the sample OLE DB destination</span></span>  
  
1.  <span data-ttu-id="8c92f-109">En el **cuadro de herramientas de SSIS**, expanda **otros destinos**y arrastre **OLE DB destino** a la superficie de diseño de la pestaña **flujo de datos** . Coloque el OLE DB destino directamente debajo de la transformación **lookup Date Key** .</span><span class="sxs-lookup"><span data-stu-id="8c92f-109">In the **SSIS Toolbox**, expand **Other Destinations**, and drag **OLE DB Destination** onto the design surface of the **Data Flow** tab. Place the OLE DB destination directly below the **Lookup Date Key** transformation.</span></span>  
  
2.  <span data-ttu-id="8c92f-110">Haga clic en la transformación **Lookup Date Key** y arrastre la flecha verde hasta el **Destino de OLE DB** que acaba de agregar para conectar los dos componentes entre sí.</span><span class="sxs-lookup"><span data-stu-id="8c92f-110">Click the **Lookup Date Key** transformation and drag the green arrow over to the newly added **OLE DB Destination** to connect the two components together.</span></span>  
  
3.  <span data-ttu-id="8c92f-111">En el cuadro de diálogo **Selección de entrada y salida** , en el cuadro de lista **Salida** , haga clic en **Salida de entradas coincidentes de búsqueda**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-111">In the **Input Output Selection** dialog box, in the **Output** list box, click **Lookup Match Output**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="8c92f-112">En la superficie de diseño **Flujo de datos** , haga clic en **Destino de OLE DB** en el componente **Destino de OLE DB** que acaba de agregar y cambie el nombre por **Sample OLE DB Destination**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-112">On the **Data Flow** design surface, click **OLE DB Destination** in the newly added **OLE DB Destination** component, and change the name to **Sample OLE DB Destination**.</span></span>  
  
5.  <span data-ttu-id="8c92f-113">Haga doble clic en **Sample OLE DB Destination**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-113">Double-click **Sample OLE DB Destination**.</span></span>  
  
6.  <span data-ttu-id="8c92f-114">En el cuadro de diálogo **Editor de destino de OLE DB** , asegúrese de que **localhost.AdventureWorksDW2012** está seleccionado en el cuadro **Administrador de conexiones OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="8c92f-114">In the **OLE DB Destination Editor** dialog box, ensure that **localhost.AdventureWorksDW2012** is selected in the **OLE DB Connection manager** box.</span></span>  
  
7.  <span data-ttu-id="8c92f-115">En el cuadro **Nombre de la tabla o la vista** , escriba o seleccione **[dbo].[FactCurrencyRate]**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-115">In the **Name of the table or the view** box, type or select **[dbo].[FactCurrencyRate]**.</span></span>  
  
8.  <span data-ttu-id="8c92f-116">Haga clic en el botón **Nuevo** para crear una nueva tabla.</span><span class="sxs-lookup"><span data-stu-id="8c92f-116">Click the **New** button to create a new table.</span></span>  <span data-ttu-id="8c92f-117">Cambie el nombre de la tabla en el script a **NewFactCurrencyRate**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-117">Change the name of the table in the script to read **NewFactCurrencyRate**.</span></span>  <span data-ttu-id="8c92f-118">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="8c92f-119">Al hacer clic en **Aceptar**, se cerrará el cuadro de diálogo y el **Nombre de la tabla o la vista** cambiará automáticamente a **NewFactCurrencyRate**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-119">Upon clicking **OK**, the dialog will close and the **Name of the table or the view** will automatically change to **NewFactCurrencyRate**.</span></span>  
  
10. <span data-ttu-id="8c92f-120">Haga clic en **Asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-120">Click **Mappings**.</span></span>  
  
11. <span data-ttu-id="8c92f-121">Compruebe que las columnas de entrada **AverageRate**, **CurrencyKey**, **EndOfDayRate**y **DateKey** están correctamente asignadas a las columnas de destino.</span><span class="sxs-lookup"><span data-stu-id="8c92f-121">Verify that the **AverageRate**, **CurrencyKey**, **EndOfDayRate**, and **DateKey** input columns are mapped correctly to the destination columns.</span></span> <span data-ttu-id="8c92f-122">Si hay columnas con el mismo nombre asignadas, la asignación es correcta.</span><span class="sxs-lookup"><span data-stu-id="8c92f-122">If same-named columns are mapped, the mapping is correct.</span></span>  
  
12. <span data-ttu-id="8c92f-123">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-123">Click **OK**.</span></span>  
  
13. <span data-ttu-id="8c92f-124">Haga clic con el botón derecho en **Sample OLE DB Destination** y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-124">Right-click the **Sample OLE DB Destination** destination and click **Properties**.</span></span>  
  
14. <span data-ttu-id="8c92f-125">En el ventana Propiedades, compruebe que la `LocaleID` propiedad está establecida en **inglés (Estados Unidos)** y que la `DefaultCodePage` propiedad está establecida en **1252**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-125">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the`DefaultCodePage` property is set to **1252**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="8c92f-126">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="8c92f-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="8c92f-127">Paso 8: Facilitar la comprensión del paquete de la lección 1</span><span class="sxs-lookup"><span data-stu-id="8c92f-127">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>](lesson-1-8-making-the-lesson-1-package-easier-to-understand.md)  
  
## <a name="see-also"></a><span data-ttu-id="8c92f-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c92f-128">See Also</span></span>  
 [<span data-ttu-id="8c92f-129">Destino de OLE DB</span><span class="sxs-lookup"><span data-stu-id="8c92f-129">OLE DB Destination</span></span>](data-flow/ole-db-destination.md)  
  
  
