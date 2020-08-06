---
title: 'Paso 4: Implementar el paquete de la lección 6 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b613cef7-7993-4d89-a429-a8251d74d435
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8c5109dc96af138bbd0c8c0087e8b73cf3bac435
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677779"
---
# <a name="step-4-deploying-the-lesson-6-package"></a><span data-ttu-id="79bac-102">Paso 4: Implementación del paquete de la lección 6</span><span class="sxs-lookup"><span data-stu-id="79bac-102">Step 4: Deploying the Lesson 6 Package</span></span>
  <span data-ttu-id="79bac-103">Implementar el paquete consiste en agregar el paquete al catálogo SSISDB de Integration Services en una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="79bac-103">Deploying the package involves adding the package to the SSISDB catalog in Integration Services on an instance of SQL Server.</span></span> <span data-ttu-id="79bac-104">En esta lección, agregará el paquete de la lección 6 en el catálogo SSISDB, establecerá el parámetro y ejecutará el paquete.</span><span class="sxs-lookup"><span data-stu-id="79bac-104">In this lesson you will add the Lesson 6 package to the SSISDB catalog, set the parameter, and execute the package.</span></span> <span data-ttu-id="79bac-105">Para esta lección, utilizará SQL Server Management Studio para agregar el paquete de la lección 6 al catálogo SSISDB e implementar el paquete.</span><span class="sxs-lookup"><span data-stu-id="79bac-105">For this lesson you will use SQL Server Management Studio to add the Lesson 6 package to the SSISDB catalog, and deploy the package.</span></span> <span data-ttu-id="79bac-106">Después de implementar el paquete, modificará el parámetro para que señale una ubicación nueva y después ejecutará el paquete.</span><span class="sxs-lookup"><span data-stu-id="79bac-106">After deploying the package you will modify the parameter to point to a new location then execute the package.</span></span>  
  
 <span data-ttu-id="79bac-107">En esta lección:</span><span class="sxs-lookup"><span data-stu-id="79bac-107">In this lesson you will:</span></span>  
  
-   <span data-ttu-id="79bac-108">Agregará el paquete al catálogo SSISDB del nodo SSIS de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="79bac-108">Add the package to the SSISDB catalog in the SSIS node in SQL Server.</span></span>  
  
-   <span data-ttu-id="79bac-109">Implementará el paquete.</span><span class="sxs-lookup"><span data-stu-id="79bac-109">Deploy the package.</span></span>  
  
-   <span data-ttu-id="79bac-110">Establecerá el valor del parámetro de paquete.</span><span class="sxs-lookup"><span data-stu-id="79bac-110">Set the package parameter value.</span></span>  
  
-   <span data-ttu-id="79bac-111">Ejecutará el paquete en SSMS.</span><span class="sxs-lookup"><span data-stu-id="79bac-111">Execute the package in SSMS.</span></span>  
  
### <a name="to-locate-or-add-the-ssisdb-catalog"></a><span data-ttu-id="79bac-112">Para buscar o agregar el catálogo SSISDB</span><span class="sxs-lookup"><span data-stu-id="79bac-112">To Locate or add the SSISDB catalog</span></span>  
  
1.  <span data-ttu-id="79bac-113">Haga clic en Inicio, señale Todos los programas, señale Microsoft SQL Server 2012 y después haga clic en SQL Management Studio.</span><span class="sxs-lookup"><span data-stu-id="79bac-113">Click Start, point to All Programs, point to Microsoft SQL Server 2012, and then click SQL Management Studio.</span></span>  
  
2.  <span data-ttu-id="79bac-114">En el cuadro de diálogo Conectar con el servidor, compruebe la configuración predeterminada y después haga clic en Conectar.</span><span class="sxs-lookup"><span data-stu-id="79bac-114">On the Connect to Server dialog box, verify the default settings, and then click Connect.</span></span> <span data-ttu-id="79bac-115">Para conectarse, el cuadro Nombre de servidor debe contener el nombre del equipo en el que SQL Server está instalado.</span><span class="sxs-lookup"><span data-stu-id="79bac-115">To connect, the Server name box must contain the name of the computer where SQL Server is installed.</span></span> <span data-ttu-id="79bac-116">Si el motor de base de datos es una instancia con nombre, el cuadro Nombre del servidor también debe contener el nombre de la instancia con el formato <nombre_equipo>\\<nombre_instancia>.</span><span class="sxs-lookup"><span data-stu-id="79bac-116">If the Database Engine is a named instance, the Server name box should also contain the instance name in the format <computer_name>\\<instance_name>.</span></span>  
  
3.  <span data-ttu-id="79bac-117">En el Explorador de objetos, expanda catálogos de Integration Services.</span><span class="sxs-lookup"><span data-stu-id="79bac-117">In Object Explorer expand Integration Services Catalogs.</span></span>  
  
4.  <span data-ttu-id="79bac-118">Si no aparece ningún catálogo en catálogos de Integration Services, agregue el catálogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="79bac-118">If there are no catalogs listed under Integration Services Catalogs then add the SSISDB catalog.</span></span>  
  
5.  <span data-ttu-id="79bac-119">Para agregar el catálogo SSISDB, haga clic con el botón derecho en catálogos de Integration Services y haga clic en Crear catálogo.</span><span class="sxs-lookup"><span data-stu-id="79bac-119">To Add the SSISDB catalog, right-click Integration Services Catalogs and click Create Catalog.</span></span>  
  
6.  <span data-ttu-id="79bac-120">En el cuadro de diálogo Crear catálogo, seleccione Habilitar integración CLR</span><span class="sxs-lookup"><span data-stu-id="79bac-120">On the Create Catalog dialog box select Enable CLR Integration.</span></span>  
  
7.  <span data-ttu-id="79bac-121">En el cuadro Contraseña, escriba una contraseña nueva y después escríbala de nuevo en el cuadro Vuelva a escribir la contraseña.</span><span class="sxs-lookup"><span data-stu-id="79bac-121">In the Password box, type a new password then type it again in the Retype Password box.</span></span> <span data-ttu-id="79bac-122">Asegúrese de recordar la contraseña que escriba.</span><span class="sxs-lookup"><span data-stu-id="79bac-122">Be sure to remember the password you type.</span></span>  
  
8.  <span data-ttu-id="79bac-123">Haga clic en Aceptar para agregar el catálogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="79bac-123">Click OK to add the SSISDB catalog.</span></span>  
  
### <a name="to-add-the-package-to-the-ssisdb-catalog"></a><span data-ttu-id="79bac-124">Para agregar el paquete en el catálogo SSISDB</span><span class="sxs-lookup"><span data-stu-id="79bac-124">To add the package to the SSISDB catalog</span></span>  
  
1.  <span data-ttu-id="79bac-125">En el Explorador de objetos, haga clic con el botón derecho en SSISDB y después en Crear carpeta.</span><span class="sxs-lookup"><span data-stu-id="79bac-125">In Object Explorer, right-click SSISDB and click Create Folder.</span></span>  
  
2.  <span data-ttu-id="79bac-126">En el cuadro de diálogo Crear carpeta, escriba Tutorial de SSIS en el cuadro Nombre de carpeta y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="79bac-126">In the Create Folder dialog box type SSIS Tutorial in the Folder name box and click OK.</span></span>  
  
3.  <span data-ttu-id="79bac-127">Expanda la carpeta Tutorial de SSIS, haga clic con el botón derecho en Proyectos y después en Importar paquetes.</span><span class="sxs-lookup"><span data-stu-id="79bac-127">Expand the SSIS Tutorial folder, right-click Projects, and click Import Packages.</span></span>  
  
4.  <span data-ttu-id="79bac-128">En la página Introducción del Asistente para la conversión de proyectos de Integration Services, haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="79bac-128">On the Integration Services Project Conversion Wizard Introduction page click Next.</span></span>  
  
5.  <span data-ttu-id="79bac-129">En la página Buscar paquetes, asegúrese de que Sistema de archivos está seleccionado en la lista de orígenes y haga clic en Examinar.</span><span class="sxs-lookup"><span data-stu-id="79bac-129">On the Locate Packages page, ensure that File system is selected in the Source list, then click Browse.</span></span>  
  
6.  <span data-ttu-id="79bac-130">En el cuadro de diálogo Buscar carpeta, vaya a la carpeta que contiene el proyecto de Tutorial de SSIS y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="79bac-130">On the Browse For Folder dialog box, browse to the folder containing the SSIS Tutorial project, then click OK.</span></span>  
  
7.  <span data-ttu-id="79bac-131">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="79bac-131">Click Next.</span></span>  
  
8.  <span data-ttu-id="79bac-132">En la página Seleccionar paquetes debería ver los seis paquetes de Tutorial de SSIS.</span><span class="sxs-lookup"><span data-stu-id="79bac-132">On the Select Packages page you should see all six packages from the SSIS Tutorial.</span></span> <span data-ttu-id="79bac-133">En la lista Paquetes, seleccione Lesson 6.dtsx y haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="79bac-133">In the Packages list, select Lesson 6.dtsx, then click Next.</span></span>  
  
9. <span data-ttu-id="79bac-134">En la página Seleccionar destino, escriba Implementación del Tutorial de SSIS en el cuadro Nombre de proyecto y haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="79bac-134">On the Select Destination page, type SSIS Tutorial Deployment in the Project Name box then click Next.</span></span>  
  
10. <span data-ttu-id="79bac-135">Haga clic en Siguiente en todas las páginas restantes del asistente hasta llegar a la página Revisar.</span><span class="sxs-lookup"><span data-stu-id="79bac-135">Click Next on each of the remaining wizard pages until you get to the Review page.</span></span>  
  
11. <span data-ttu-id="79bac-136">En la página Revisar, haga clic en Convertir.</span><span class="sxs-lookup"><span data-stu-id="79bac-136">On the Review page, click Convert.</span></span>  
  
12. <span data-ttu-id="79bac-137">Cuando se complete la conversión, haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="79bac-137">When the conversion completes, click Close.</span></span>  
  
 <span data-ttu-id="79bac-138">Al cerrar el Asistente para la conversión de proyectos de Integration Services, SSIS muestra el Asistente para implementación de Integration Services.</span><span class="sxs-lookup"><span data-stu-id="79bac-138">When you close the Integration Services Project Conversion Wizard, SSIS displays the Integration Services Deployment Wizard.</span></span> <span data-ttu-id="79bac-139">Ahora utilizará a este asistente para implementar el paquete de la lección 6.</span><span class="sxs-lookup"><span data-stu-id="79bac-139">You will use this wizard now to deploy the Lesson 6 package.</span></span>  
  
1.  <span data-ttu-id="79bac-140">En la página Introducción del Asistente para implementación de Integration Services, revise los pasos para implementar el proyecto y haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="79bac-140">On the Integration Services Deployment Wizard Introduction page, review the steps for deploying the project, then click Next.</span></span>  
  
2.  <span data-ttu-id="79bac-141">En la página Seleccionar destino, compruebe que el nombre de servidor es la instancia de SQL Server que contiene el catálogo SSISDB y que la ruta de acceso muestra la Implementación del Tutorial de SSIS; después, haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="79bac-141">On the Select Destination page verify that the server name is the instance of SQL Server containing the SSISDB catalog and that the path shows SSIS Tutorial Deployment, then click Next.</span></span>  
  
3.  <span data-ttu-id="79bac-142">En la página Revisar, revise el Resumen y después haga clic en implementar.</span><span class="sxs-lookup"><span data-stu-id="79bac-142">On the Review page, review the Summary then click Deploy.</span></span>  
  
4.  <span data-ttu-id="79bac-143">Cuando se complete la implementación, haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="79bac-143">When the deployment completes, click Close.</span></span>  
  
5.  <span data-ttu-id="79bac-144">En el Explorador de objetos, haga clic con el botón derecho en Catálogos de Integration Services y después en Actualizar.</span><span class="sxs-lookup"><span data-stu-id="79bac-144">In Object Explorer, right-click Integration Services Catalogs and click Refresh.</span></span>  
  
6.  <span data-ttu-id="79bac-145">Expanda los Catálogos de Integration Services y después SSISDB.</span><span class="sxs-lookup"><span data-stu-id="79bac-145">Expand Integration Services Catalogs then expand SSISDB.</span></span> <span data-ttu-id="79bac-146">Continúe expandiendo el árbol por debajo de Tutorial de SSIS hasta haber expandido el proyecto por completo.</span><span class="sxs-lookup"><span data-stu-id="79bac-146">Continue to Expand the tree under SSIS Tutorial until you have completely expanded the project.</span></span> <span data-ttu-id="79bac-147">Debería ver Lesson 6.dtsx debajo del nodo Paquetes del nodo Implementación del Tutorial de SSIS.</span><span class="sxs-lookup"><span data-stu-id="79bac-147">You should see Lesson 6.dtsx under the Packages node of the SSIS Tutorial Deployment node.</span></span>  
  
 <span data-ttu-id="79bac-148">Para comprobar que el paquete está completo, haga clic en Lesson 6.dtsx y después en Configurar.</span><span class="sxs-lookup"><span data-stu-id="79bac-148">To verify that the package is complete, right-click Lesson 6.dtsx and click Configure.</span></span> <span data-ttu-id="79bac-149">En el cuadro de diálogo Configurar, seleccione Parámetros y compruebe que existe una entrada con Lesson 6.dtsx como Contenedor, VarFolderName como Nombre y la ruta de acceso a Nuevos datos de ejemplo como valor y después haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="79bac-149">On the Configure dialog box, select Parameters and verify that there is an entry with Lesson 6.dtsx as the Container, VarFolderName as the Name and the path to New Sample Data as the value, then click Close.</span></span>  
  
 <span data-ttu-id="79bac-150">Antes de continuar, cree una nueva carpeta de datos de ejemplo, asígnele el nombre Datos de ejemplo dos y copie cualquiera de los tres archivos de ejemplo originales en ella.</span><span class="sxs-lookup"><span data-stu-id="79bac-150">Before continuing create a new sample data folder, name it Sample Data Two, and copy any three of the original sample files into it.</span></span>  
  
### <a name="to-create-and-populate-a-new-sample-data-folder"></a><span data-ttu-id="79bac-151">Para crear y rellenar una carpeta nueva de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="79bac-151">To create and populate a new sample data folder</span></span>  
  
1.  <span data-ttu-id="79bac-152">En el Explorador de Windows, en el nivel de raíz de la unidad (por ejemplo, C:\\), cree una carpeta nueva denominada Datos de ejemplo dos.</span><span class="sxs-lookup"><span data-stu-id="79bac-152">In Windows Explorer, at the root level of your drive (for example, C:\\), create a new folder named Sample Data Two.</span></span>  
  
2.  <span data-ttu-id="79bac-153">Abra la carpeta c:\Archivos de programa\Microsoft SQL Server\110\Ejemplos\Servicios de integración\Tutorial\Creating a Simple ETL Package\Datos de muestra y, después, copie cualquiera de los tres archivos de ejemplo de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="79bac-153">Open the c:\Program Files\Microsoft SQL Server\110\Samples\Integration Services\Tutorial\Creating a Simple ETL Package\Sample Data folder and then copy any three of the sample files from the folder.</span></span>  
  
3.  <span data-ttu-id="79bac-154">En la carpeta Nuevos datos de ejemplo, pegue los archivos copiados.</span><span class="sxs-lookup"><span data-stu-id="79bac-154">In the New Sample Data folder, paste the copied files.</span></span>  
  
### <a name="to-change-the-package-parameter-to-point-to-the-new-sample-data"></a><span data-ttu-id="79bac-155">Para cambiar el parámetro de paquete para que señale a los nuevos datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="79bac-155">To change the package parameter to point to the new sample data</span></span>  
  
1.  <span data-ttu-id="79bac-156">En el Explorador de objetos, haga clic con el botón derecho en Lesson 6.dtsx y después en Configurar.</span><span class="sxs-lookup"><span data-stu-id="79bac-156">In Object Explorer, right click Lesson 6.dtsx and click Configure.</span></span>  
  
2.  <span data-ttu-id="79bac-157">En el cuadro de diálogo Configurar, cambie el valor de parámetro a la ruta de acceso a Datos de ejemplo dos.</span><span class="sxs-lookup"><span data-stu-id="79bac-157">On the Configure dialog box, change the parameter value to the path to Sample Data Two.</span></span> <span data-ttu-id="79bac-158">Por ejemplo, C:\Datos de ejemplo dos si ha colocado la nueva carpeta en la carpeta raíz de la unidad C.</span><span class="sxs-lookup"><span data-stu-id="79bac-158">For example C:\Sample Data Two if you placed the new folder in the root folder on the C drive.</span></span>  
  
3.  <span data-ttu-id="79bac-159">Haga clic en Aceptar para cerrar el cuadro de diálogo Configurar.</span><span class="sxs-lookup"><span data-stu-id="79bac-159">Click OK to close the Configure dialog box.</span></span>  
  
### <a name="to-test-the-lesson-6-package-deployment"></a><span data-ttu-id="79bac-160">Para probar la implementación del paquete de la lección 6</span><span class="sxs-lookup"><span data-stu-id="79bac-160">To test the Lesson 6 package deployment</span></span>  
  
1.  <span data-ttu-id="79bac-161">En el Explorador de objetos, haga clic con el botón derecho en Lesson 6.dtsx y después en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="79bac-161">In Object Explorer, right click Lesson 6.dtsx and click Execute.</span></span>  
  
2.  <span data-ttu-id="79bac-162">En el cuadro de diálogo Ejecutar paquete, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="79bac-162">On the Execute Package dialog box, click OK.</span></span>  
  
3.  <span data-ttu-id="79bac-163">En el cuadro de diálogo del mensaje, haga clic en Sí para abrir el informe de información general.</span><span class="sxs-lookup"><span data-stu-id="79bac-163">On the message dialog box click Yes to open Overview Report.</span></span>  
  
 <span data-ttu-id="79bac-164">Se visualiza el informe información general del paquete, que muestra el nombre del paquete y un resumen de estado.</span><span class="sxs-lookup"><span data-stu-id="79bac-164">The Overview report for the package is displayed showing the name of the package and a status summary.</span></span> <span data-ttu-id="79bac-165">La sección Información general de ejecución muestra el resultado de cada tarea del paquete y la sección Parámetros usados muestra los nombres y valores de todos los parámetros utilizados en la ejecución del paquete, incluido VarFolderName.</span><span class="sxs-lookup"><span data-stu-id="79bac-165">The Execution Overview section shows the result from each task in the package and the Parameters Used section shows the names and values of all parameters used in the package execution, including VarFolderName.</span></span>  
  
  
