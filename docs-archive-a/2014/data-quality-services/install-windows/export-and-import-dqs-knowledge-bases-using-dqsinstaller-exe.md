---
title: Exportar e importar bases de conocimiento de DQS mediante DQSInstaller.exe | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 8234c63b-a018-4e55-8184-9a6bdf03274d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 64a8feb7bfded742da7563642b07181166fcbeab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748259"
---
# <a name="export-and-import-dqs-knowledge-bases-using-dqsinstallerexe"></a><span data-ttu-id="dd3bf-102">Exportar e importar bases de conocimiento de DQS mediante DQSInstaller.exe</span><span class="sxs-lookup"><span data-stu-id="dd3bf-102">Export and Import DQS Knowledge Bases Using DQSInstaller.exe</span></span>
  <span data-ttu-id="dd3bf-103">En el caso de una instalación existente de DQS, puede exportar simultáneamente todas las bases de conocimiento de [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] a un archivo de copia de seguridad de DQS (.dqsb) y utilizar después dicho archivo .dqsb para importar simultáneamente todas las bases de conocimiento en otro [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] mediante la ejecución del archivo DQSInstaller.exe desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="dd3bf-103">For an existing installation of DQS, you can export all the knowledge bases in your [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] to a DQS backup file (.dqsb) at once, and then later use the .dqsb file to import all the knowledge bases to a different [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] at once by running the DQSInstaller.exe file from the command prompt.</span></span> <span data-ttu-id="dd3bf-104">Para obtener más información acerca de cómo s ejecuta DQSInstaller.exe desde el símbolo del sistema, vea [Ejecutar DQSInstaller.exe desde el símbolo del sistema](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#CommandPrompt) en [Ejecutar DQSInstaller.exe para completar la instalación del servidor de calidad de datos](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="dd3bf-104">For more information about running DQSInstaller.exe from the command prompt, see [Run DQSInstaller.exe from Command Prompt](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#CommandPrompt) in [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
 <span data-ttu-id="dd3bf-105">Esta característica permite realizar una copia de seguridad de *todas* las bases de conocimiento de [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] simultáneamente sin necesidad de exportar individualmente cada una de ellas a un archivo .dqs usando [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd3bf-105">This feature enables you to take a backup of *all* your knowledge bases in [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] at once without having to individually export each knowledge base to a .dqs file by using [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)].</span></span> <span data-ttu-id="dd3bf-106">Asimismo, puede importar *todas* las bases de conocimiento del archivo de copia de seguridad en otro [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] simultáneamente sin necesidad de importar individualmente cada una de ellas desde un archivo .dqs usando [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd3bf-106">Similarly, you can import *all* the knowledge bases from the backup file into another [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] at once without having to individually import each knowledge base from a .dqs file by using [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)].</span></span> <span data-ttu-id="dd3bf-107">Esto resulta particularmente útil para hacer una copia de seguridad de las bases de conocimiento y restaurarlas durante la desinstalación de [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] de un equipo y su posterior instalación en otro.</span><span class="sxs-lookup"><span data-stu-id="dd3bf-107">This is particularly useful for backing up and restoring your knowledge bases when you are uninstalling [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] on a computer, and then reinstalling it on a different computer.</span></span> <span data-ttu-id="dd3bf-108">Puede exportar fácilmente todas las bases de conocimiento de una instalación de [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] existente a un archivo de copia de seguridad de DQS (.dqsb) y, a continuación, importarlas desde el archivo de copia de seguridad después de haber instalado [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="dd3bf-108">You can easily export all the knowledge bases in an existing installation of [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] to a DQS backup file (.dqsb), and then import all the knowledge bases from the backup file after installing [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] on a different computer.</span></span>  
  
##  <a name="exporting-knowledge-bases-to-dqsb-file"></a><a name="export"></a><span data-ttu-id="dd3bf-109">Exportar bases de conocimiento a un archivo. dqsb</span><span class="sxs-lookup"><span data-stu-id="dd3bf-109">Exporting Knowledge Bases to .dqsb File</span></span>  
 <span data-ttu-id="dd3bf-110">Puede exportar todas las bases de conocimiento de un [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] existente en cualquier momento o al desinstalar [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd3bf-110">You can export all the knowledge bases in the existing [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] at any time or while uninstalling [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)].</span></span>  
  
-   <span data-ttu-id="dd3bf-111">Para exportar todas las bases de conocimiento de [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] a un archivo de copia de seguridad de DQS (.dqsb), ejecute DQSInstaller.exe con el parámetro `exportkbs` desde el símbolo del sistema, junto con la ruta de acceso completa y el nombre de archivo donde desea exportar las bases de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="dd3bf-111">To export all the knowledge bases in a [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] to a DQS backup file (.dqsb), run DQSInstaller.exe with the `exportkbs` parameter from the command prompt, along with the full path and file name where you want to export the knowledge bases.</span></span> <span data-ttu-id="dd3bf-112">Por ejemplo, para exportar todas las bases de conocimiento al archivo DQSBackup.dqsb de la unidad C:</span><span class="sxs-lookup"><span data-stu-id="dd3bf-112">For example, to export all the knowledge bases to the DQSBackup.dqsb file in the C: drive:</span></span>  
  
    ```  
    dqsinstaller.exe -exportkbs c:\DQSBackup.dqsb  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="dd3bf-113">Si el nombre de archivo especificado ya existe en la ubicación especificada, el instalador le preguntará si desea sobrescribir el archivo.</span><span class="sxs-lookup"><span data-stu-id="dd3bf-113">If the provided file name already exists at the specified location, the installer prompts you whether to overwrite the file.</span></span>  
  
-   <span data-ttu-id="dd3bf-114">Para exportar todas las bases de conocimiento a un archivo de copia de seguridad de DQS mientras desinstala [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)], ejecute DQSInstaller.exe con el parámetro `uninstall` desde el símbolo del sistema, junto con la ruta de acceso completa y el nombre de archivo donde desea exportar las bases de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="dd3bf-114">To export all the knowledge bases to a DQS backup file while uninstalling [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)], run DQSInstaller.exe with the `uninstall` parameter from the command prompt, along with the full path and file name where you want to export the knowledge bases.</span></span> <span data-ttu-id="dd3bf-115">Por ejemplo, para exportar todas las bases de conocimiento al archivo DQSBackup.dqsb de la unidad C: y, a continuación, desinstalar [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="dd3bf-115">For example, to export all the knowledge bases to the DQSBackup.dqsb file in the C: drive, and then uninstall [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)]:</span></span>  
  
    ```  
    dqsinstaller.exe -uninstall c:\DQSBackup.dqsb  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="dd3bf-116">Si no especifica la ruta de acceso completa y el nombre del archivo de copia de seguridad de DQS al desinstalar [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] desde el símbolo del sistema con el parámetro `uninstall` , se mostrará un mensaje indicando que se eliminarán todas las bases de conocimiento y permitiéndole elegir entre continuar o no con el proceso de desinstalación.</span><span class="sxs-lookup"><span data-stu-id="dd3bf-116">If you do not specify the full path and file name of the DQS backup file while uninstalling [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] from the command prompt using the `uninstall` parameter, a message is displayed stating that all the knowledge bases will be deleted, and allows you to choose whether to continue with the uninstall process.</span></span>  
  
##  <a name="importing-knowledge-bases-from-dqsb-file"></a><a name="import"></a><span data-ttu-id="dd3bf-117">Importar bases de conocimiento desde un archivo. dqsb</span><span class="sxs-lookup"><span data-stu-id="dd3bf-117">Importing Knowledge Bases from .dqsb File</span></span>  
 <span data-ttu-id="dd3bf-118">Puede importar todas las bases de conocimiento desde un archivo de copia de seguridad de DQS (.dqsb) después de completar la instalación de [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd3bf-118">You can import all the knowledge bases from a DQS backup file (.dqsb) after completing the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installation.</span></span> <span data-ttu-id="dd3bf-119">Para importar bases de conocimiento, debe tener un archivo de copia de seguridad de DQS (.dqsb) válido.</span><span class="sxs-lookup"><span data-stu-id="dd3bf-119">To import knowledge bases, you must have a valid DQS backup file (.dqsb).</span></span>  
  
 <span data-ttu-id="dd3bf-120">Ejecute el archivo DQSInstaller.exe con el parámetro `importkbs` desde el símbolo del sistema, junto con la ruta de acceso completa y el nombre de archivo del que desea importar las bases de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="dd3bf-120">Run the DQSInstaller.exe file with the `importkbs` parameter from the command prompt, along with the full path and file name from where you want to import the knowledge bases.</span></span> <span data-ttu-id="dd3bf-121">Por ejemplo, para importar todas las bases de conocimiento desde el archivo DQSBackup.dqsb de la unidad C:</span><span class="sxs-lookup"><span data-stu-id="dd3bf-121">For example, to import all the knowledge bases from the DQSBackup.dqsb file in the C: drive:</span></span>  
  
```  
dqsinstaller.exe -importkbs c:\DQSBackup.dqsb  
```  
  
 <span data-ttu-id="dd3bf-122">Si ya existen bases de conocimiento en [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] que tienen el mismo nombre que las que va a importar, a los nombres de las bases de datos importadas se les agregará un carácter de subrayado (_) seguido de un valor entero, comenzando por 1.</span><span class="sxs-lookup"><span data-stu-id="dd3bf-122">If there are existing knowledge bases in your [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] with the same name as the ones you are importing, the names of the imported knowledge bases will be appended with an underscore (_) followed by an integer value starting with 1.</span></span> <span data-ttu-id="dd3bf-123">Por ejemplo, si el dominio "CompanyName" está duplicado, el nombre del dominio importado será "CompanyName_1".</span><span class="sxs-lookup"><span data-stu-id="dd3bf-123">For example, if the "CompanyName" domain is duplicate, the imported domain name will be "CompanyName_1."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd3bf-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd3bf-124">See Also</span></span>  
 <span data-ttu-id="dd3bf-125">[Ejecutar DQSInstaller.exe para completar la instalación del servidor de calidad de datos](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="dd3bf-125">[Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md) </span></span>  
 <span data-ttu-id="dd3bf-126">[Instalar Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="dd3bf-126">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 <span data-ttu-id="dd3bf-127">[Exportar una base de conocimiento a un archivo. DQS](../export-a-knowledge-base-to-a-dqs-file.md) </span><span class="sxs-lookup"><span data-stu-id="dd3bf-127">[Export a Knowledge Base to a .dqs File](../export-a-knowledge-base-to-a-dqs-file.md) </span></span>  
 [<span data-ttu-id="dd3bf-128">Importar una base de conocimiento desde un archivo .dqs</span><span class="sxs-lookup"><span data-stu-id="dd3bf-128">Import a Knowledge Base from a .dqs File</span></span>](../import-a-knowledge-base-from-a-dqs-file.md)  
  
  