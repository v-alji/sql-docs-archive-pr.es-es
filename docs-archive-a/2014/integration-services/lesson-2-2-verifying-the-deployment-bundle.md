---
title: 'Paso 2: Comprobar el conjunto de implementación | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 6c13f5c9-c75e-4e52-94dc-2d2db2c578fe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f452a87154175ac05a050761d8f12b6bfe61cd8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663581"
---
# <a name="step-2-verifying-the-deployment-bundle"></a><span data-ttu-id="ef5ac-102">Paso 2: Comprobación del paquete de implementación</span><span class="sxs-lookup"><span data-stu-id="ef5ac-102">Step 2: Verifying the Deployment Bundle</span></span>
  <span data-ttu-id="ef5ac-103">En la lección 1, ha creado el proyecto Deployment Tutorial y le ha agregado paquetes y archivos auxiliares; en la tarea anterior, ha creado una utilidad de implementación para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ef5ac-103">In lesson 1, you created the Deployment Tutorial project and added packages and ancillary files to the project; in the previous task you built a deployment utility for the project.</span></span>  
  
 <span data-ttu-id="ef5ac-104">En esta tarea, comprobará el contenido del paquete de implementación.</span><span class="sxs-lookup"><span data-stu-id="ef5ac-104">In this task, you will verify the contents of the deployment bundle.</span></span> <span data-ttu-id="ef5ac-105">El paquete de implementación es la carpeta que copiará en el equipo de destino y que usará para instalar paquetes.</span><span class="sxs-lookup"><span data-stu-id="ef5ac-105">The deployment bundle is the folder that you will copy to the destination computer and use to install packages.</span></span> <span data-ttu-id="ef5ac-106">Si ha usado el valor predeterminado (bin\Deployment) como ubicación de la utilidad de implementación, el paquete de implementación estará en la carpeta Bin\Deployment dentro de la carpeta Deployment Tutorial del proyecto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef5ac-106">If you used the default value-bin\Deployment-as the location of the deployment utility, the deployment bundle is the Bin\Deployment folder within the Deployment Tutorial folder in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
### <a name="to-verify-the-content-of-deployment-bundle"></a><span data-ttu-id="ef5ac-107">Para comprobar el contenido del paquete de implementación</span><span class="sxs-lookup"><span data-stu-id="ef5ac-107">To verify the content of deployment bundle</span></span>  
  
1.  <span data-ttu-id="ef5ac-108">Busque la carpeta bin\Deployment en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ef5ac-108">Locate the bin\Deployment folder on your computer.</span></span>  
  
2.  <span data-ttu-id="ef5ac-109">Compruebe que están presentes los archivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ef5ac-109">Verify that the following files are present:</span></span>  
  
    -   <span data-ttu-id="ef5ac-110">DataTransfer.dtsx</span><span class="sxs-lookup"><span data-stu-id="ef5ac-110">DataTransfer.dtsx</span></span>  
  
    -   <span data-ttu-id="ef5ac-111">datatransferconfig.dtsconfig</span><span class="sxs-lookup"><span data-stu-id="ef5ac-111">datatransferconfig.dtsconfig</span></span>  
  
    -   <span data-ttu-id="ef5ac-112">Deployment Tutorial.SSISDeploymentManifest</span><span class="sxs-lookup"><span data-stu-id="ef5ac-112">Deployment Tutorial.SSISDeploymentManifest</span></span>  
  
    -   <span data-ttu-id="ef5ac-113">LoadXMLData.dtsx</span><span class="sxs-lookup"><span data-stu-id="ef5ac-113">LoadXMLData.dtsx</span></span>  
  
    -   <span data-ttu-id="ef5ac-114">loadxmldataconfig.dtsconfig</span><span class="sxs-lookup"><span data-stu-id="ef5ac-114">loadxmldataconfig.dtsconfig</span></span>  
  
    -   <span data-ttu-id="ef5ac-115">NewCustomers.txt</span><span class="sxs-lookup"><span data-stu-id="ef5ac-115">NewCustomers.txt</span></span>  
  
    -   <span data-ttu-id="ef5ac-116">orders.xml</span><span class="sxs-lookup"><span data-stu-id="ef5ac-116">orders.xml</span></span>  
  
    -   <span data-ttu-id="ef5ac-117">orders.xsd</span><span class="sxs-lookup"><span data-stu-id="ef5ac-117">orders.xsd</span></span>  
  
    -   <span data-ttu-id="ef5ac-118">Readme.txt</span><span class="sxs-lookup"><span data-stu-id="ef5ac-118">Readme.txt</span></span>  
  
3.  <span data-ttu-id="ef5ac-119">Haga clic con el botón derecho en Deployment Tutorial.SSISDeploymentManifest, elija **Abrir con**y, después, haga clic en **Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="ef5ac-119">Right-click Deployment Tutorial.SSISDeploymentManifest, point **to Open With**, and then click **Internet Explorer**.</span></span> <span data-ttu-id="ef5ac-120">También puede abrir el archivo en un editor de texto como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="ef5ac-120">You can also open the file in a text editor such as Notepad.</span></span> <span data-ttu-id="ef5ac-121">El código XML del archivo debe ser el siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef5ac-121">The XML code of the file should be the following:</span></span>  
  
     `<?xml version="1.0"?><DTSDeploymentManifest GeneratedBy="Domain\UserName" GeneratedFromProjectName="Deployment Tutorial" GeneratedDate="2006-02-24T13:29:02.6537669-08:00" AllowConfigurationChanges="true"><Package>DataTransfer.dtsx</Package><Package>LoadXMLData.dtsx</Package><ConfigurationFile>datatransferconfig.dtsconfig</ConfigurationFile><ConfigurationFile>loadxmldataconfig.dtsconfig</ConfigurationFile><MiscellaneousFile>Readme.txt</MiscellaneousFile><MiscellaneousFile>orders.xml</MiscellaneousFile><MiscellaneousFile>NewCustomers.txt</MiscellaneousFile><MiscellaneousFile>orders.xsd</MiscellaneousFile></DTSDeploymentManifest>`  
  
4.  <span data-ttu-id="ef5ac-122">Compruebe que el valor del `AllowConfigurationChanges` atributo es **true** y que el código XML incluye un `Package` elemento para cada uno de los dos paquetes, un `MiscellaneousFile` elemento para cada uno de los cuatro archivos que no son de paquete y un `ConfigurationFile` elemento para cada uno de los dos archivos de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="ef5ac-122">Verify that the value of the `AllowConfigurationChanges` attribute is **true** and the XML includes a `Package` element for each of the two packages, a `MiscellaneousFile` element for each of the four non-package files, and a `ConfigurationFile` element for each of the two XML configuration files.</span></span>  
  
5.  <span data-ttu-id="ef5ac-123">Salga de Internet Explorer o del editor de texto.</span><span class="sxs-lookup"><span data-stu-id="ef5ac-123">Exit Internet Explorer or the text editor.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="ef5ac-124">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="ef5ac-124">Next Lesson</span></span>  
 [<span data-ttu-id="ef5ac-125">Lección 3: Instalar paquetes</span><span class="sxs-lookup"><span data-stu-id="ef5ac-125">Lesson 3: Installing Packages</span></span>](../integration-services/lesson-3-install-ssis-package.md)  
  
<span data-ttu-id="ef5ac-126">![Integration Services icono (pequeño)](media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ef5ac-126">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ef5ac-127">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="ef5ac-127">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ef5ac-128">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="ef5ac-128">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ef5ac-129">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="ef5ac-129">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
