---
title: 'Paso 4: Agregar un destino de archivo plano | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f4088de3-16d8-419c-96a1-a2cd005d0a5b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: eff65f4a94a412d55af8055e302195f87ae4cdb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747693"
---
# <a name="step-4-adding-a-flat-file-destination"></a><span data-ttu-id="7e346-102">Paso 4: Adición de un destino de archivo plano</span><span class="sxs-lookup"><span data-stu-id="7e346-102">Step 4: Adding a Flat File Destination</span></span>
  <span data-ttu-id="7e346-103">La salida de errores de la transformación Lookup Currency Key redirige a la transformación Script cualquier fila de datos que haya generado un error durante la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7e346-103">The error output of the Lookup Currency Key transformation redirects to the Script transformation any data rows that failed the lookup operation.</span></span> <span data-ttu-id="7e346-104">Para mejorar la información acerca de los errores producidos, la transformación Script ejecuta un script que obtiene una descripción de los errores.</span><span class="sxs-lookup"><span data-stu-id="7e346-104">To enhance information about the errors that occurred, the Script transformation runs a script that gets the description of errors.</span></span>  
  
 <span data-ttu-id="7e346-105">En esta tarea guardará toda esta información acerca de las filas con errores en un archivo delimitado para su procesamiento posterior.</span><span class="sxs-lookup"><span data-stu-id="7e346-105">In this task, you will save all this information about the failed rows to a delimited file for later processing.</span></span> <span data-ttu-id="7e346-106">Para guardar las filas con errores, es preciso agregar y configurar un administrador de conexiones de archivos planos para el archivo de texto que contendrá los datos de error y un destino de archivo plano.</span><span class="sxs-lookup"><span data-stu-id="7e346-106">To save the failed rows, you must add and configure a Flat File connection manager for the text file that will contain the error data and a Flat File destination.</span></span> <span data-ttu-id="7e346-107">Al establecer propiedades en el administrador de conexiones de archivos planos que usa el destino de archivo plano, puede especificar la manera en que el destino de archivo plano establece el formato y escribe el archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7e346-107">By setting properties on the Flat File connection manager that the Flat File destination uses, you can specify how the Flat File destination formats and writes the text file.</span></span> <span data-ttu-id="7e346-108">Para obtener más información, vea [Administrador de conexiones de archivos planos](connection-manager/file-connection-manager.md) y [destino de archivo plano](data-flow/flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="7e346-108">For more information, see [Flat File Connection Manager](connection-manager/file-connection-manager.md) and [Flat File Destination](data-flow/flat-file-destination.md).</span></span>  
  
### <a name="to-add-and-configure-a-flat-file-destination"></a><span data-ttu-id="7e346-109">Para agregar y configurar un destino de archivo plano</span><span class="sxs-lookup"><span data-stu-id="7e346-109">To add and configure a Flat File destination</span></span>  
  
1.  <span data-ttu-id="7e346-110">Haga clic en la pestaña **Flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="7e346-110">Click the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="7e346-111">En el **Cuadro de herramientas de SSIS**, expanda **Otros**y arrastre **Destino de archivo plano** a la superficie de diseño del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="7e346-111">In the **SSIS Toolbox**, expand **Other**, and drag **Flat File Destination** onto the data flow design surface.</span></span> <span data-ttu-id="7e346-112">Coloque el **Destino de archivo plano** directamente debajo de la transformación **Get Error Description** .</span><span class="sxs-lookup"><span data-stu-id="7e346-112">Put the **Flat File Destination** directly underneath the **Get Error Description** transformation.</span></span>  
  
3.  <span data-ttu-id="7e346-113">Haga clic en la transformación **Get Error Description** y arrastre la flecha verde hasta el nuevo **Destino de archivo plano**.</span><span class="sxs-lookup"><span data-stu-id="7e346-113">Click the **Get Error Description** transformation, and then drag the green arrow onto the new **Flat File Destination**.</span></span>  
  
4.  <span data-ttu-id="7e346-114">En la superficie de diseño **Flujo de datos** , haga clic en **Destino de archivo plano** en la transformación **Destino de archivo plano** recién agregada y cambie el nombre a **Failed Rows**.</span><span class="sxs-lookup"><span data-stu-id="7e346-114">On the **Data Flow** design surface, click **Flat File Destination** in the newly added **Flat File Destination** transformation, and change the name to **Failed Rows**.</span></span>  
  
5.  <span data-ttu-id="7e346-115">Haga clic con el botón derecho en la transformación **Failed Rows** , haga clic en **Editar**y, después, en el **Editor de destino de archivos planos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7e346-115">Right-click the **Failed Rows** transformation, click **Edit**, and then in the **Flat File Destination Editor**, click **New**.</span></span>  
  
6.  <span data-ttu-id="7e346-116">En el cuadro de diálogo **Formato de archivo plano** , compruebe que esté seleccionado **Delimitado** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7e346-116">In the **Flat File Format** dialog box, verify that **Delimited** is selected, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="7e346-117">En el **Editor del administrador de conexiones de archivos planos**, en el cuadro **nombre del administrador de conexiones** , escriba `Error Data` .</span><span class="sxs-lookup"><span data-stu-id="7e346-117">In the **Flat File Connection Manager Editor**, in the **Connection Manager Name** box type `Error Data`.</span></span>  
  
8.  <span data-ttu-id="7e346-118">En el cuadro de diálogo **Editor del administrador de conexiones de archivos planos** , haga clic en **Examinar**y busque la carpeta en la que se almacenará el archivo.</span><span class="sxs-lookup"><span data-stu-id="7e346-118">In the **Flat File Connection Manager Editor** dialog box, click **Browse**, and locate the folder in which to store the file.</span></span>  
  
9. <span data-ttu-id="7e346-119">En el cuadro de diálogo **abrir** , en **nombre de archivo**, escriba y, `ErrorOutput.txt` a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="7e346-119">In the **Open** dialog box, for **File name**, type `ErrorOutput.txt`, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="7e346-120">En el cuadro de diálogo **Editor del administrador de conexiones de archivos planos** , compruebe que el cuadro **Configuración regional** contiene Inglés (Estados Unidos) y la **Página de códigos** contiene 1252 (ANSI -Latin I).</span><span class="sxs-lookup"><span data-stu-id="7e346-120">In the **Flat File Connection Manager Editor** dialog box, verify that the **Locale** box contains English (United States) and **Code page** contains 1252 (ANSI -Latin I).</span></span>  
  
11. <span data-ttu-id="7e346-121">En el panel de opciones, haga clic en **Columnas**.</span><span class="sxs-lookup"><span data-stu-id="7e346-121">In the options pane, click **Columns**.</span></span>  
  
     <span data-ttu-id="7e346-122">Observe que, además de las columnas del archivo de datos de origen, existen tres columnas nuevas: ErrorCode, ErrorColumn y ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="7e346-122">Notice that, in addition to the columns from the source data file, three new columns are present: ErrorCode, ErrorColumn, and ErrorDescription.</span></span> <span data-ttu-id="7e346-123">Estas columnas las generan la salida de errores de la transformación Lookup Currency Key y el script de la transformación Get Error Description y pueden utilizarse para solucionar el problema de la fila que genera el error.</span><span class="sxs-lookup"><span data-stu-id="7e346-123">These columns are generated by the error output of the Lookup Currency Key transformation and by the script in the Get Error Description transformation, and can be used to troubleshoot the cause of the failed row.</span></span>  
  
12. <span data-ttu-id="7e346-124">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e346-124">Click **OK**.</span></span>  
  
13. <span data-ttu-id="7e346-125">En el **Editor de destino de archivos planos**, desactive la casilla **Sobrescribir los datos del archivo** .</span><span class="sxs-lookup"><span data-stu-id="7e346-125">In the **Flat File Destination Editor**, clear the **Overwrite data in the file** check box.</span></span>  
  
     <span data-ttu-id="7e346-126">Al desactivar esta casilla, se conservan los errores sobre múltiples ejecuciones del paquete.</span><span class="sxs-lookup"><span data-stu-id="7e346-126">Clearing this check box persists the errors over multiple package executions.</span></span>  
  
14. <span data-ttu-id="7e346-127">En el **Editor de destino de archivos planos**, haga clic **Asignaciones** para comprobar que todas las columnas son correctas.</span><span class="sxs-lookup"><span data-stu-id="7e346-127">In the **Flat File Destination Editor**, click **Mappings** to verify that all the columns are correct.</span></span> <span data-ttu-id="7e346-128">Si lo desea, puede cambiar el nombre de las columnas en el destino.</span><span class="sxs-lookup"><span data-stu-id="7e346-128">Optionally, you can rename the columns in the destination.</span></span>  
  
15. <span data-ttu-id="7e346-129">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e346-129">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7e346-130">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7e346-130">Next Steps</span></span>  
 [<span data-ttu-id="7e346-131">Paso 5: Prueba del paquete del tutorial de la lección 4</span><span class="sxs-lookup"><span data-stu-id="7e346-131">Step 5: Testing the Lesson 4 Tutorial Package</span></span>](../integration-services/lesson-4-5-testing-the-lesson-4-tutorial-package.md)  
  
  
