---
title: Instalar Distributed Replay mediante un archivo de configuración | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3259232c-6963-4c9c-9d10-ae42aa262eef
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7757cce29c2e6b3ce4f1e91fc97cbf8be02ae521
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747906"
---
# <a name="install-distributed-replay-using-a-configuration-file"></a><span data-ttu-id="e6c92-102">Instalar Distributed Replay utilizando un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="e6c92-102">Install Distributed Replay Using a Configuration File</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e6c92-103">permite generar un archivo de configuración basado en la entrada de usuario y en la configuración predeterminada del sistema.</span><span class="sxs-lookup"><span data-stu-id="e6c92-103">Setup provides the ability to generate a configuration file based on user input and system defaults.</span></span> <span data-ttu-id="e6c92-104">Si especifica que desea que se instalen las herramientas de administración, puede utilizar el archivo de configuración para implementar los tres componentes de Distributed Replay (herramienta de administración, controlador de Distributed Replay y cliente Distributed Replay).</span><span class="sxs-lookup"><span data-stu-id="e6c92-104">If you specify that you want the Management tools installed, you can use the configuration file to deploy the three Distributed Replay components (administration tool, Distributed Replay controller, and the Distributed Replay client).</span></span> <span data-ttu-id="e6c92-105">Admite la instalación, reparación y desinstalación de los componentes de Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="e6c92-105">It supports Installing, repairing, and uninstalling of the Distributed Replay components.</span></span>  
  
 <span data-ttu-id="e6c92-106">El programa de instalación admite el uso del archivo de configuración solamente a través de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e6c92-106">Setup supports the use of the configuration file only through the command-line.</span></span> <span data-ttu-id="e6c92-107">A continuación se indica el orden de procesamiento de los parámetros cuando se usa el archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="e6c92-107">The processing order of the parameters while using the configuration file is outlined below:</span></span>  
  
-   <span data-ttu-id="e6c92-108">El archivo de configuración sobrescribe los valores predeterminados de un paquete.</span><span class="sxs-lookup"><span data-stu-id="e6c92-108">The configuration file overwrites the defaults in a package</span></span>  
  
-   <span data-ttu-id="e6c92-109">Los valores de línea de comandos sobrescriben los valores del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e6c92-109">Command-line values overwrite the values in the configuration file</span></span>  
  
 <span data-ttu-id="e6c92-110">Para obtener más información sobre cómo usar un archivo de configuración, consulte [instalación de SQL Server 2014 mediante un archivo de configuración](../../database-engine/install-windows/install-sql-server-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="e6c92-110">For more information about how to use a configuration file, see [Install SQL Server 2014 Using a Configuration File](../../database-engine/install-windows/install-sql-server-using-a-configuration-file.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e6c92-111">Después de instalar Distributed Replay, debe crear las reglas de firewall en los equipos cliente y de controlador, y conceder a cada equipo cliente permisos en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="e6c92-111">After you install Distributed Replay you must create firewall rules on the controller and client computers, and grant each client computer permissions on the target server.</span></span> <span data-ttu-id="e6c92-112">Para obtener más información, vea [Completar los pasos posteriores a la instalación](../../tools/distributed-replay/complete-the-post-installation-steps.md).</span><span class="sxs-lookup"><span data-stu-id="e6c92-112">For more information, see [Complete the Post-Installation Steps](../../tools/distributed-replay/complete-the-post-installation-steps.md).</span></span>  
  
### <a name="to-generate-a-configuration-file"></a><span data-ttu-id="e6c92-113">Para generar un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="e6c92-113">To generate a configuration file</span></span>  
  
1.  <span data-ttu-id="e6c92-114">Siga los pasos del asistente para instalación hasta llegar a la página **Listo para instalar** .</span><span class="sxs-lookup"><span data-stu-id="e6c92-114">Follow the Setup wizard through to the **Ready to Install** page.</span></span> <span data-ttu-id="e6c92-115">La ruta de acceso al archivo de configuración se especifica en la sección que así lo indica en la página **Listo para instalar** .</span><span class="sxs-lookup"><span data-stu-id="e6c92-115">The path to the configuration file is specified in the **Ready to Install** page in the configuration file path section.</span></span>  
  
2.  <span data-ttu-id="e6c92-116">Cancele la instalación sin completarla realmente para generar el archivo INI.</span><span class="sxs-lookup"><span data-stu-id="e6c92-116">Cancel the setup without actually completing the installation, to generate the INI file.</span></span>  
  
### <a name="to-install-distributed-replay-using-the-configuration-file"></a><span data-ttu-id="e6c92-117">Para instalar Distributed Replay utilizando el archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="e6c92-117">To Install Distributed Replay Using the Configuration File</span></span>  
  
-   <span data-ttu-id="e6c92-118">Realice la instalación utilizando el símbolo del sistema y proporcione el archivo ConfigurationFile.ini mediante el parámetro ConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="e6c92-118">Run the installation through the command prompt and supply the ConfigurationFile.ini using the ConfigurationFile parameter.</span></span>  
  
 <span data-ttu-id="e6c92-119">**Sintaxis de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="e6c92-119">**Sample Syntax**</span></span>  
  
 <span data-ttu-id="e6c92-120">A continuación figura un ejemplo sobre cómo especificar el archivo de configuración en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="e6c92-120">Following is an example on how to specify the configuration file at the command prompt:</span></span>  
  
```  
Setup.exe /CTLRSVCPASSWORD="ctlrsvcpswd" /CLTSVCPASSWORD="cltsvcpswd" / ConfigurationFile=ConfigurationFile.INI\  
```  
  
> [!NOTE]  
>  <span data-ttu-id="e6c92-121">Debe especificar ambas contraseñas en la línea de comandos porque no puede configurarlas en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e6c92-121">You must specify both passwords in the command line because you cannot configure them in the configuration file.</span></span>  
  
  
