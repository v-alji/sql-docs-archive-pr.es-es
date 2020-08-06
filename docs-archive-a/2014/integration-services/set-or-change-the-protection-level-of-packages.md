---
title: Establecer o cambiar el nivel de protección de los paquetes | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- passwords [Integration Services]
- packages [Integration Services],security
- security [Integration Services],protection levels
- protection level for packages [Integration Services]
ms.assetid: 904a5580-82ba-4a26-b0c5-d1c989975f61
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da8e63028498097b4321e4ef1383fbc8aa5845b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750025"
---
# <a name="set-or-change-the-protection-level-of-packages"></a><span data-ttu-id="6bc5f-102">Establecer o cambiar el nivel de protección de los paquetes</span><span class="sxs-lookup"><span data-stu-id="6bc5f-102">Set or Change the Protection Level of Packages</span></span>
  <span data-ttu-id="6bc5f-103">Para controlar el acceso al contenido de los paquetes y a los valores confidenciales que contienen, como las contraseñas, establezca el valor de la propiedad `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-103">To control access to the contents of packages and to the sensitive values that they contain, such as passwords, set the value of the `ProtectionLevel` property.</span></span> <span data-ttu-id="6bc5f-104">Los paquetes que se incluyen en un proyecto deben disponer del mismo nivel de protección que el proyecto con el fin de compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-104">The packages contained in a project need to have the same protection level as the project, to build the project.</span></span> <span data-ttu-id="6bc5f-105">Si cambia la configuración de las propiedades de `ProtectionLevel` en el proyecto, debe actualizar manualmente el valor de la propiedad de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-105">If you change the `ProtectionLevel` property setting on the project, you need to manually update the property setting for the packages.</span></span>  
  
 <span data-ttu-id="6bc5f-106">Para obtener información acerca de cómo determinar las `ProtectionLevel` Opciones de configuración adecuadas para los paquetes en diferentes fases del ciclo de vida del paquete, consulte [Access Control de datos confidenciales en paquetes](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="6bc5f-106">For information about how to determine the `ProtectionLevel` settings that are appropriate for your packages at different stages in the package life cycle, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span> <span data-ttu-id="6bc5f-107">Para obtener información general sobre las características de seguridad de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], vea [Información general sobre seguridad &#40;Integration Services&#41;](security/security-overview-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="6bc5f-107">For an overview of security features in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], see [Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md).</span></span>  
  
 <span data-ttu-id="6bc5f-108">Los procedimientos de este tema describen cómo utilizar [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] o la utilidad de símbolo del sistema dtutil para cambiar la propiedad `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-108">The procedures in this topic describe how to use either [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] or the dtutil command prompt utility to change the `ProtectionLevel` property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6bc5f-109">Además de los procedimientos de este tema, normalmente puede establecer o cambiar la propiedad `ProtectionLevel` de un paquete al importarlo o exportarlo.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-109">In addition to the procedures in this topic, you can typically set or change the `ProtectionLevel` property of a package when you import or export the package.</span></span> <span data-ttu-id="6bc5f-110">También puede cambiar la propiedad `ProtectionLevel` de un paquete al utilizar el Asistente para importación y exportación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para guardarlo.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-110">You can also change the `ProtectionLevel` property of a package when you use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard to save a package.</span></span>  
  
### <a name="to-set-or-change-the-protection-level-of-a-package-in-sql-server-data-tools"></a><span data-ttu-id="6bc5f-111">Para establecer o cambiar el nivel de protección de un paquete en herramientas de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6bc5f-111">To set or change the protection level of a package in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="6bc5f-112">Revise los valores disponibles para la `ProtectionLevel` propiedad en el tema [establecimiento del nivel de protección de los paquetes](security/access-control-for-sensitive-data-in-packages.md)y determine el valor adecuado para el paquete.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-112">Review the available values for the `ProtectionLevel` property in the topic, [Setting the Protection Level of Packages](security/access-control-for-sensitive-data-in-packages.md), and determine the appropriate value for your package.</span></span>  
  
2.  <span data-ttu-id="6bc5f-113">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package.</span></span>  
  
3.  <span data-ttu-id="6bc5f-114">Abra el paquete en el diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6bc5f-114">Open the package in the [!INCLUDE[ssIS](../includes/ssis-md.md)] designer.</span></span>  
  
4.  <span data-ttu-id="6bc5f-115">Si la ventana Propiedades no muestra las propiedades del paquete, haga clic en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-115">If the Properties window does not show the properties of the package, click the design surface.</span></span>  
  
5.  <span data-ttu-id="6bc5f-116">En el ventana Propiedades, en el grupo **seguridad** , seleccione el valor adecuado para la `ProtectionLevel` propiedad.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-116">In the Properties window, in the **Security** group, select the appropriate value for the `ProtectionLevel` property.</span></span>  
  
     <span data-ttu-id="6bc5f-117">Si selecciona un nivel de protección que requiere una contraseña, escríbala como valor de la propiedad **PackagePassword** .</span><span class="sxs-lookup"><span data-stu-id="6bc5f-117">If you select a protection level that requires a password, enter the password as the value of the **PackagePassword** property.</span></span>  
  
6.  <span data-ttu-id="6bc5f-118">En el menú **Archivo** , seleccione **Guardar los elementos seleccionados** para guardar el paquete modificado.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-118">On the **File** menu, select **Save Selected Items** to save the modified package.</span></span>  
  
### <a name="to-set-or-change-the-protection-level-of-packages-at-the-command-prompt"></a><span data-ttu-id="6bc5f-119">Para establecer o cambiar el nivel de protección de los paquetes en el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="6bc5f-119">To set or change the protection level of packages at the command prompt</span></span>  
  
1.  <span data-ttu-id="6bc5f-120">Revise los valores disponibles para la `ProtectionLevel` propiedad en el tema [establecimiento del nivel de protección de los paquetes](security/access-control-for-sensitive-data-in-packages.md)y determine el valor adecuado para el paquete.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-120">Review the available values for the `ProtectionLevel` property in the topic, [Setting the Protection Level of Packages](security/access-control-for-sensitive-data-in-packages.md), and determine the appropriate value for your package.</span></span>  
  
2.  <span data-ttu-id="6bc5f-121">Revise las asignaciones de la `Encrypt` opción en el tema de la [utilidad DTUtil](dtutil-utility.md)y determine el entero adecuado que se va a utilizar como valor de la `ProtectionLevel` propiedad seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-121">Review the mappings for the `Encrypt` option in the topic, [dtutil Utility](dtutil-utility.md), and determine the appropriate integer to use as the value of the selected `ProtectionLevel` property.</span></span>  
  
3.  <span data-ttu-id="6bc5f-122">Abra una ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-122">Open a Command Prompt window.</span></span>  
  
4.  <span data-ttu-id="6bc5f-123">En el símbolo del sistema, navegue a la carpeta que contiene el paquete o paquetes para los que desea establecer la propiedad `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-123">At the command prompt, navigate to the folder that contains the package or packages for which you want to set the `ProtectionLevel` property.</span></span>  
  
     <span data-ttu-id="6bc5f-124">Los ejemplos de sintaxis mostrados en el paso siguiente suponen que esta carpeta es la actual.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-124">The syntax examples shown in the following step assume that this folder is the current folder.</span></span>  
  
5.  <span data-ttu-id="6bc5f-125">Establezca o cambie el nivel de protección del paquete o paquetes utilizando un comando similar al de los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6bc5f-125">Set or change the protection level of the package or packages by using a command similar to the one of the following examples:</span></span>  
  
    -   <span data-ttu-id="6bc5f-126">El comando siguiente establece la propiedad `ProtectionLevel` de un paquete individual en el sistema de archivos en el nivel 2, "Cifrado confidencial con contraseña", con la contraseña "strongpassword":</span><span class="sxs-lookup"><span data-stu-id="6bc5f-126">The following command sets the `ProtectionLevel` property of an individual package in the file system to level 2, "Encrypt sensitive with password", with the password, "strongpassword":</span></span>  
  
         `dtutil.exe /file "C:\Package.dtsx" /encrypt file;"C:\Package.dtsx";2;strongpassword`  
  
    -   <span data-ttu-id="6bc5f-127">El comando siguiente establece la propiedad `ProtectionLevel` de todos los paquetes en una carpeta concreta del sistema de archivos en el nivel 2, "Cifrado confidencial con contraseña", con la contraseña "strongpassword":</span><span class="sxs-lookup"><span data-stu-id="6bc5f-127">The following command sets the `ProtectionLevel` property of all packages in a particular folder in the file system to level 2, "Encrypt sensitive with password", with the password, "strongpassword":</span></span>  
  
         `for %f in (*.dtsx) do dtutil.exe /file %f /encrypt file;%f;2;strongpassword`  
  
         <span data-ttu-id="6bc5f-128">Si utiliza un comando similar en un archivo por lotes, escriba el marcador de posición del archivo, "% f", como "%% f" en el archivo por lotes.</span><span class="sxs-lookup"><span data-stu-id="6bc5f-128">If you use a similar command in a batch file, enter the file placeholder, "%f", as "%%f" in the batch file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bc5f-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6bc5f-129">See Also</span></span>  
 [<span data-ttu-id="6bc5f-130">dtutil (utilidad)</span><span class="sxs-lookup"><span data-stu-id="6bc5f-130">dtutil Utility</span></span>](dtutil-utility.md)  
  
  
