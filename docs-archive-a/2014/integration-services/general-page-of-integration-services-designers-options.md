---
title: Página general | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Business_Intelligence_Designers.Data_Transformation_Designers.General
ms.assetid: d695690a-923b-4036-945e-7621e8651deb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 59073ac29f95f1e64bd0a9382366e9539ce1408a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663600"
---
# <a name="general-page"></a><span data-ttu-id="f39f6-102">Página General</span><span class="sxs-lookup"><span data-stu-id="f39f6-102">General Page</span></span>
  <span data-ttu-id="f39f6-103">Utilice la página **General** de la página **Diseñadores de Integration Services** en el cuadro de diálogo **Opciones** con el fin de especificar las opciones para cargar, mostrar y actualizar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="f39f6-103">Use the **General** page of the **Integration Services Designers** page in the **Options** dialog box to specify the options for loading, displaying, and upgrading packages.</span></span>  
  
 <span data-ttu-id="f39f6-104">Para abrir la página **General** , en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], en el menú **Herramientas** , haga clic en **Opciones**, expanda **Diseñadores de Business Intelligence**y seleccione **Diseñadores de Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="f39f6-104">To open the **General** page, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Tools** menu, click **Options**, expand **Business Intelligence Designers**, and select **Integration Services Designers**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f39f6-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="f39f6-105">Options</span></span>  
 <span data-ttu-id="f39f6-106">**Comprobar la firma digital al cargar un paquete**</span><span class="sxs-lookup"><span data-stu-id="f39f6-106">**Check digital signature when loading a package**</span></span>  
 <span data-ttu-id="f39f6-107">Seleccione para que [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] compruebe la firma digital al cargar un paquete.</span><span class="sxs-lookup"><span data-stu-id="f39f6-107">Select to have [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] check the digital signature when loading a package.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="f39f6-108">solo realizará la comprobación si la firma digital está presente, es válida y procede de un origen de confianza.</span><span class="sxs-lookup"><span data-stu-id="f39f6-108">will only check whether the digital signature is present, is valid, and is from a trusted source.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="f39f6-109">no comprobará si el paquete ha cambiado desde que se firmó.</span><span class="sxs-lookup"><span data-stu-id="f39f6-109">will not check whether the package has been changed since the package was signed.</span></span>  
  
 <span data-ttu-id="f39f6-110">Si establece el valor del Registro **BlockedSignatureStates** , este valor del Registro invalida la opción **Comprobar la firma digital al cargar un paquete** .</span><span class="sxs-lookup"><span data-stu-id="f39f6-110">If you set the **BlockedSignatureStates** registry value, this registry value overrides the **Check digital signature when loading a package** option.</span></span> <span data-ttu-id="f39f6-111">Para más información, vea [Implementar una directiva de firma estableciendo un valor del Registro](implement-a-signing-policy-by-setting-a-registry-value.md).</span><span class="sxs-lookup"><span data-stu-id="f39f6-111">For more information, see [Implement a Signing Policy by Setting a Registry Value](implement-a-signing-policy-by-setting-a-registry-value.md).</span></span>  
  
 <span data-ttu-id="f39f6-112">Para más información sobre los paquetes y los certificados digitales, vea [Identificar el origen de paquetes con firmas digitales](security/identify-the-source-of-packages-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="f39f6-112">For more information about digital certificates and packages, see [Identify the Source of Packages with Digital Signatures](security/identify-the-source-of-packages-with-digital-signatures.md).</span></span>  
  
 <span data-ttu-id="f39f6-113">**Mostrar una advertencia si un paquete está sin firmar**</span><span class="sxs-lookup"><span data-stu-id="f39f6-113">**Show warning if package is unsigned**</span></span>  
 <span data-ttu-id="f39f6-114">Seleccione esta opción para mostrar una advertencia cuando se carga un paquete que está sin firmar.</span><span class="sxs-lookup"><span data-stu-id="f39f6-114">Select to display a warning when loading a package that is not signed.</span></span>  
  
 <span data-ttu-id="f39f6-115">**Mostrar etiquetas de restricción de precedencia**</span><span class="sxs-lookup"><span data-stu-id="f39f6-115">**Show precedence constraint labels**</span></span>  
 <span data-ttu-id="f39f6-116">Seleccione la etiqueta que quiere que se muestre (Correcto, Error o Conclusión) en restricciones de precedencia al visualizar paquetes en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f39f6-116">Select which label-Success, Failure, or Completion-to display on precedence constraints when viewing packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="f39f6-117">**Lenguaje de scripting**</span><span class="sxs-lookup"><span data-stu-id="f39f6-117">**Scripting language**</span></span>  
 <span data-ttu-id="f39f6-118">Seleccione el lenguaje de scripting predeterminado para las nuevas tareas Script y los componentes Script.</span><span class="sxs-lookup"><span data-stu-id="f39f6-118">Select the default scripting language for new Script tasks and Script components.</span></span>  
  
 <span data-ttu-id="f39f6-119">**Actualizar las cadenas de conexión para reflejar los nuevos nombres de proveedor**</span><span class="sxs-lookup"><span data-stu-id="f39f6-119">**Update connection strings to use new provider names**</span></span>  
 <span data-ttu-id="f39f6-120">Al abrir o actualizar paquetes de [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] , actualice las cadenas de conexión para que usen los nombres de los proveedores siguientes para la versión actual de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f39f6-120">When opening or upgrading [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] packages, update connection strings to use the names for the following providers, for the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="f39f6-121">Proveedor OLE DB</span><span class="sxs-lookup"><span data-stu-id="f39f6-121">OLE DB provider</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="f39f6-122">Native Client</span><span class="sxs-lookup"><span data-stu-id="f39f6-122">Native Client</span></span>  
  
 <span data-ttu-id="f39f6-123">El Asistente para actualizar paquetes de [!INCLUDE[ssIS](../includes/ssis-md.md)] solo actualiza las cadenas de conexión que se almacenan en administradores de conexiones.</span><span class="sxs-lookup"><span data-stu-id="f39f6-123">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard updates only connection strings that are stored in connection managers.</span></span> <span data-ttu-id="f39f6-124">No actualiza las cadenas de conexión que se construyen dinámicamente utilizando el lenguaje de expresiones de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] o código en una tarea Script.</span><span class="sxs-lookup"><span data-stu-id="f39f6-124">The wizard does not update connection strings that are constructed dynamically by using the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] expression language, or by using code in a Script task.</span></span>  
  
 <span data-ttu-id="f39f6-125">**Crear el identificador del nuevo paquete**</span><span class="sxs-lookup"><span data-stu-id="f39f6-125">**Create new package ID**</span></span>  
 <span data-ttu-id="f39f6-126">Al actualizar paquetes de [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] , cree los identificadores de los paquetes nuevos para las versiones actualizadas de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="f39f6-126">When upgrading [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] packages, create new package IDs for the upgraded versions of the packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f39f6-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f39f6-127">See Also</span></span>  
 <span data-ttu-id="f39f6-128">[Información general sobre seguridad &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="f39f6-128">[Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span></span>  
 [<span data-ttu-id="f39f6-129">Ampliar paquetes con scripting</span><span class="sxs-lookup"><span data-stu-id="f39f6-129">Extending Packages with Scripting</span></span>](extending-packages-scripting/extending-packages-with-scripting.md)  
  
  
