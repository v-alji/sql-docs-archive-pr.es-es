---
title: Desempaquetar un paquete DAC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- wizard [DAC], unpack
- data-tier application [SQL Server], unpack
- How to [DAC], unpack
- unpack DAC
ms.assetid: 697b69b3-f157-4e22-ac4e-f65c5fc2d0ad
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ba0930f79a47696a6c9a9c1bfe028316601f64b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677672"
---
# <a name="unpack-a-dac-package"></a><span data-ttu-id="fc1a5-102">Desempaquetar un paquete de DAC</span><span class="sxs-lookup"><span data-stu-id="fc1a5-102">Unpack a DAC Package</span></span>
  <span data-ttu-id="fc1a5-103">Utilice el diálogo Unpack Data-tier Application para descomprimir los scripts y archivos de un paquete de la aplicación de capa de datos (DAC).</span><span class="sxs-lookup"><span data-stu-id="fc1a5-103">Use the Unpack Data-tier Application dialog box to unzip the scripts and files from a data-tier application (DAC) package.</span></span> <span data-ttu-id="fc1a5-104">Los scripts y archivos se colocan en una carpeta donde se pueden revisar antes de usar el paquete para implementar la DAC en un sistema de producción.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-104">The scripts and files are placed in a folder where they can be reviewed before the package is used to deploy the DAC into a production system.</span></span> <span data-ttu-id="fc1a5-105">El contenido de una DAC también se puede comparar con el contenido de otro paquete desempaquetado en otra carpeta.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-105">The contents of one DAC can also be compared with the contents of another package unpacked to another folder.</span></span>  
  
1.  <span data-ttu-id="fc1a5-106">**Antes de empezar:**  [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="fc1a5-106">**Before you begin:**  [Security](#Security)</span></span>  
  
2.  <span data-ttu-id="fc1a5-107">**Para desempaquetar un paquete DAC con:**  [cuadro de diálogo Desempaquetar aplicación de capa de datos](#UnpackDACDial), [Examinar el contenido de un paquete DAC](#ExamDACPack)</span><span class="sxs-lookup"><span data-stu-id="fc1a5-107">**To unpack a DAC, using:**  [Unpack Data-tier Application Dialog](#UnpackDACDial), [Examine the Contents of a DAC Package](#ExamDACPack)</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fc1a5-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fc1a5-108">Security</span></span>  
 <span data-ttu-id="fc1a5-109">Se recomienda no implementar un paquete DAC desde orígenes desconocidos o que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-109">We recommend that you do not deploy a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="fc1a5-110">Es posible que estas DAC contengan código malintencionado que podría ejecutar código [!INCLUDE[tsql](../../includes/tsql-md.md)] no deseado o provocar errores al modificar el esquema.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-110">Such DACs could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema.</span></span> <span data-ttu-id="fc1a5-111">Antes de usar una DAC de un origen desconocido o que no es de confianza, impleméntela en una instancia de prueba aislada de [!INCLUDE[ssDE](../../includes/ssde-md.md)], desempaquete la DAC y examine el código, como los procedimientos almacenados o el código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-111">Before you use a DAC from an unknown or untrusted source, deploy it on an isolated test instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], unpack the DAC and examine the code, such as stored procedures or other user-defined code.</span></span>  
  
##  <a name="unpack-data-tier-application-dialog"></a><a name="UnpackDACDial"></a> <span data-ttu-id="fc1a5-112">Cuadro de diálogo Desempaquetar aplicación de capa de datos</span><span class="sxs-lookup"><span data-stu-id="fc1a5-112">Unpack Data-tier Application Dialog</span></span>  
 <span data-ttu-id="fc1a5-113">**Para desempaquetar un archivo de paquete DAC**</span><span class="sxs-lookup"><span data-stu-id="fc1a5-113">**To Unpack a DAC Package File**</span></span>  
  
-   <span data-ttu-id="fc1a5-114">En el **Explorador de Windows**, vaya a la ubicación de un archivo de paquete DAC (.dacpac).</span><span class="sxs-lookup"><span data-stu-id="fc1a5-114">In **Windows Explorer**, navigate to the location of a DAC package (.dacpac) file.</span></span>  
  
-   <span data-ttu-id="fc1a5-115">Use uno de estos dos métodos para abrir el cuadro de diálogo Desempaquetar aplicación de capa de datos:</span><span class="sxs-lookup"><span data-stu-id="fc1a5-115">Use one of these two methods to open the Unpack Data-tier Application dialog:</span></span>  
  
    1.  <span data-ttu-id="fc1a5-116">Haga clic con el botón derecho en el archivo de paquete DAC (.dacpac) y seleccione **Desempaquetar**.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-116">Right-click the DAC package (.dacpac) file and select **Unpack**.</span></span>  
  
    2.  <span data-ttu-id="fc1a5-117">Haga doble clic en el archivo de paquete DAC.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-117">Double-click the DAC package file.</span></span>  
  
-   <span data-ttu-id="fc1a5-118">Complete los cuadros de diálogo:</span><span class="sxs-lookup"><span data-stu-id="fc1a5-118">Complete the dialogs:</span></span>  
  
    -   [<span data-ttu-id="fc1a5-119">Desempaquetar archivo de paquete DAC de Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="fc1a5-119">Unpack Microsoft SQL Server DAC Package File</span></span>](#Unpack)  
  
    -   [<span data-ttu-id="fc1a5-120">Buscar carpeta</span><span class="sxs-lookup"><span data-stu-id="fc1a5-120">Browse for Folder</span></span>](#Browse)  
  
###  <a name="unpack-microsoft-sql-server-dac-package-file"></a><a name="Unpack"></a> <span data-ttu-id="fc1a5-121">Desempaquetar archivo de paquete DAC de Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="fc1a5-121">Unpack Microsoft SQL Server DAC Package File</span></span>  
 <span data-ttu-id="fc1a5-122">Use esta página para especificar la carpeta de destino en la que colocar los archivos desempaquetados y, a continuación, proceda a desempaquetar los archivos.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-122">Use this page to specify the destination folder in which to place the unpacked files, and then run the unpack operation.</span></span>  
  
 <span data-ttu-id="fc1a5-123">**Los archivos se desempaquetarán en esta carpeta:** Especifique la ruta de acceso completa a la carpeta para los archivos desempaquetados.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-123">**Files will be unpacked to this folder:** - Specify the full path to the folder for the unpacked files.</span></span> <span data-ttu-id="fc1a5-124">Si la carpeta existe y conoce la ruta de acceso completa, escriba la ruta en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-124">If the folder exists and you know the full path, type the path in the box.</span></span> <span data-ttu-id="fc1a5-125">Si no, haga clic en el botón **Examinar** para navegar hasta una carpeta o crear una nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-125">If not, click the **Browse** button to navigate to a folder or create a new folder.</span></span>  
  
 <span data-ttu-id="fc1a5-126">**Examinar** Abre la página **Buscar carpeta** donde puede seleccionar una carpeta si examina la jerarquía de archivos, o crear una nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-126">**Browse** - Opens the **Browse for Folder** page where you can choose a folder by navigating the file hierarchy, or create a new folder.</span></span>  
  
 <span data-ttu-id="fc1a5-127">**Desempaquetar** Comienza a desempaquetar los archivos.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-127">**Unpack** - Starts the unpack operation.</span></span>  
  
 <span data-ttu-id="fc1a5-128">**Cancelar** Cierra el cuadro de diálogo sin desempaquetar el paquete DAC.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-128">**Cancel** - Terminates the dialog box without unpacking the DAC package.</span></span>  
  
###  <a name="browse-for-folder"></a><a name="Browse"></a> <span data-ttu-id="fc1a5-129">Buscar carpeta</span><span class="sxs-lookup"><span data-stu-id="fc1a5-129">Browse for Folder</span></span>  
 <span data-ttu-id="fc1a5-130">Use esta página para elegir la carpeta de destino para desempaquetar los archivos.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-130">Use this page to choose the destination folder for the unpack operation.</span></span> <span data-ttu-id="fc1a5-131">Opcionalmente, también puede crear una nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-131">Optionally, you can also create a new folder.</span></span>  
  
 <span data-ttu-id="fc1a5-132">**Lista de carpetas** Muestra la jerarquía de archivos del equipo.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-132">**Folder list** - Displays the file hierarchy for your computer.</span></span> <span data-ttu-id="fc1a5-133">Expanda los nodos para navegar hasta la carpeta en la que desempaquetar el paquete DAC.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-133">Expand the nodes to navigate to the folder in which to unpack the DAC package.</span></span> <span data-ttu-id="fc1a5-134">Haga clic en la carpeta y luego en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-134">Click on the folder and then click **OK**.</span></span>  
  
 <span data-ttu-id="fc1a5-135">**Crear nueva carpeta** Abre un cuadro de diálogo en el que puede especificar el nombre de una nueva carpeta que se va a crear en la carpeta que ha seleccionado en la jerarquía de carpetas.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-135">**Make New Folder** - Opens a dialog in which you can specify the name for a new folder to be created in the folder you have currently selected in the folder hierarchy.</span></span>  
  
 <span data-ttu-id="fc1a5-136">**Aceptar** Coloca la ruta de acceso de la carpeta que seleccionó en el cuadro **Los archivos se desempaquetarán en esta carpeta** de la página **Desempaquetar archivo de paquete DAC** y le devuelve a esa página.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-136">**OK** - Places the path to the folder you selected in the **Files will be unpacked to this folder** box of the **Unpack DAC Package File** page and returns you to that page.</span></span>  
  
 <span data-ttu-id="fc1a5-137">**Cancelar** Cierra el cuadro de diálogo sin seleccionar una carpeta.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-137">**Cancel** - Terminates the dialog box without selecting a folder.</span></span>  
  
##  <a name="examine-the-contents-of-a-dac-package"></a><a name="ExamDACPack"></a> <span data-ttu-id="fc1a5-138">Examinar el contenido de un paquete DAC</span><span class="sxs-lookup"><span data-stu-id="fc1a5-138">Examine the Contents of a DAC Package</span></span>  
 <span data-ttu-id="fc1a5-139">Después de desempaquetar el paquete, puede examinar los archivos generados por el cuadro de diálogo **Desempaquetar aplicación de capa de datos** .</span><span class="sxs-lookup"><span data-stu-id="fc1a5-139">After unpacking the package, you can examine the files produced by the **Unpack Data-tier Application** dialog.</span></span> <span data-ttu-id="fc1a5-140">El cuadro de diálogo compila los siguientes archivos en la carpeta de destino seleccionada:</span><span class="sxs-lookup"><span data-stu-id="fc1a5-140">The dialog box builds the following files in the selected destination folder:</span></span>  
  
1.  <span data-ttu-id="fc1a5-141">Un script Transact-SQL que contiene las instrucciones para crear los objetos definidos en la DAC.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-141">A Transact-SQL script that contains the statements for creating the objects defined in the DAC.</span></span> <span data-ttu-id="fc1a5-142">El nombre de archivo es *NombreDAC*.sql, donde *NombreDAC* es el nombre de la DAC.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-142">The file name is *DACName*.sql, where *DACName* is the name of the DAC.</span></span>  
  
2.  <span data-ttu-id="fc1a5-143">Todos los archivos XML del paquete.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-143">All XML files from the package.</span></span>  
  
3.  <span data-ttu-id="fc1a5-144">Todos los archivos de la sección de archivos adicionales de la DAC, como los archivos previos y posteriores a la implementación.</span><span class="sxs-lookup"><span data-stu-id="fc1a5-144">All files from the Extra Files section of the DAC, such as the DAC pre-deployment or post-deployment files.</span></span>  
  
 <span data-ttu-id="fc1a5-145">Para obtener más información, consulte [Validate a DAC Package](validate-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="fc1a5-145">For more information, see [Validate a DAC Package](validate-a-dac-package.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc1a5-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc1a5-146">See Also</span></span>  
 <span data-ttu-id="fc1a5-147">[Aplicaciones de capa de datos](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="fc1a5-147">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="fc1a5-148">[Implementar una aplicación de capa de datos](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="fc1a5-148">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 [<span data-ttu-id="fc1a5-149">Actualizar una aplicación de capa de datos</span><span class="sxs-lookup"><span data-stu-id="fc1a5-149">Upgrade a Data-tier Application</span></span>](upgrade-a-data-tier-application.md)  
  
  
