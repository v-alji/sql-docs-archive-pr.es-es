---
title: Implementar una directiva de firma estableciendo un valor del registro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- signing policies [Integration Services]
ms.assetid: 64f6966f-2292-401f-acb1-2ccb5aee484a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1e844b65df5b45f212554f7583f4e4b327b740e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663588"
---
# <a name="implement-a-signing-policy-by-setting-a-registry-value"></a><span data-ttu-id="47dac-102">Implementar una directiva de firma estableciendo un valor del Registro</span><span class="sxs-lookup"><span data-stu-id="47dac-102">Implement a Signing Policy by Setting a Registry Value</span></span>
  <span data-ttu-id="47dac-103">Se puede usar un valor opcional del Registro para administrar la directiva de una organización para la carga de paquetes firmados o sin firmar.</span><span class="sxs-lookup"><span data-stu-id="47dac-103">You can use an optional registry value to manage an organization's policy for loading signed or unsigned packages.</span></span> <span data-ttu-id="47dac-104">Si utiliza este valor del Registro, debe crearlo en cada equipo en el que se ejecutarán los paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] y en el que desea exigir el cumplimiento de la directiva.</span><span class="sxs-lookup"><span data-stu-id="47dac-104">If you use this registry value, you must create this registry value on each computer on which [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages will run and on which you want to enforce the policy.</span></span> <span data-ttu-id="47dac-105">Una vez establecido el valor del Registro, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] comprobará las firmas antes de cargar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="47dac-105">After the registry value has been set, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] will check or verify the signatures before loading packages.</span></span>  
  
 <span data-ttu-id="47dac-106">En este procedimiento de este tema se describe cómo agregar el valor DWORD opcional `BlockedSignatureStates` a la clave del Registro HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span><span class="sxs-lookup"><span data-stu-id="47dac-106">This procedure in this topic describes how to add the optional `BlockedSignatureStates` DWORD value to the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS registry key.</span></span> <span data-ttu-id="47dac-107">El valor de los datos de `BlockedSignatureStates` determina si se debe bloquear un paquete que tenga una firma que no sea de confianza, una firma no válida, o que esté sin firmar.</span><span class="sxs-lookup"><span data-stu-id="47dac-107">The data value in `BlockedSignatureStates` determines whether a package should be blocked if it has an untrusted signature, has an invalid signature, or is unsigned.</span></span> <span data-ttu-id="47dac-108">Con respecto al estado de las firmas que se utilizan para firmar paquetes, el valor del Registro `BlockedSignatureStates` usa las siguientes definiciones:</span><span class="sxs-lookup"><span data-stu-id="47dac-108">With regard to the status of signatures used to sign packages, the `BlockedSignatureStates` registry value uses the following definitions:</span></span>  
  
-   <span data-ttu-id="47dac-109">Una *firma válida* es una firma que puede leerse correctamente.</span><span class="sxs-lookup"><span data-stu-id="47dac-109">A *valid signature* is one that can be read successfully.</span></span>  
  
-   <span data-ttu-id="47dac-110">Una *firma no válida* es una firma para la que la suma de comprobación descifrada (algoritmo hash unidireccional del código de paquete cifrado con una clave privada) no coincide con la suma de comprobación descifrada que se calcula como parte del proceso de carga de paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="47dac-110">An *invalid signature* is one for which the decrypted checksum (the one-way hash of the package code encrypted by a private key) does not match the decrypted checksum that is calculated as part of the process of loading [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span>  
  
-   <span data-ttu-id="47dac-111">Una *firma de confianza* es una firma creada mediante un certificado digital firmado por una entidad de certificación raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="47dac-111">A *trusted signature* is one that is created by using a digital certificate signed by a Trusted Root Certification Authority.</span></span> <span data-ttu-id="47dac-112">Este valor de configuración no exige que el firmante se encuentre en la lista de publicadores de confianza del usuario.</span><span class="sxs-lookup"><span data-stu-id="47dac-112">This setting does not require the signer to be found in the user's list of Trusted Publishers.</span></span>  
  
-   <span data-ttu-id="47dac-113">Una *firma que no es de confianza* es una firma que no se puede comprobar que haya sido emitida por una entidad de certificación raíz de confianza o una firma que no es actual.</span><span class="sxs-lookup"><span data-stu-id="47dac-113">An *untrusted signature* is one that cannot be verified as issued by a Trusted Root Certification Authority, or a signature that is not current.</span></span>  
  
 <span data-ttu-id="47dac-114">En la tabla siguiente se enumeran los valores válidos de los datos DWORD y su directiva asociada.</span><span class="sxs-lookup"><span data-stu-id="47dac-114">The following table lists the valid values of the DWORD data and their associated policy.</span></span>  
  
|<span data-ttu-id="47dac-115">Value</span><span class="sxs-lookup"><span data-stu-id="47dac-115">Value</span></span>|<span data-ttu-id="47dac-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="47dac-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="47dac-117">0</span><span class="sxs-lookup"><span data-stu-id="47dac-117">0</span></span>|<span data-ttu-id="47dac-118">Sin restricción administrativa.</span><span class="sxs-lookup"><span data-stu-id="47dac-118">No administrative restriction.</span></span>|  
|<span data-ttu-id="47dac-119">1</span><span class="sxs-lookup"><span data-stu-id="47dac-119">1</span></span>|<span data-ttu-id="47dac-120">Bloquear firmas no válidas.</span><span class="sxs-lookup"><span data-stu-id="47dac-120">Block invalid signatures.</span></span><br /><br /> <span data-ttu-id="47dac-121">Este valor no bloquea los paquetes sin firmar.</span><span class="sxs-lookup"><span data-stu-id="47dac-121">This setting does not block unsigned packages.</span></span>|  
|<span data-ttu-id="47dac-122">2</span><span class="sxs-lookup"><span data-stu-id="47dac-122">2</span></span>|<span data-ttu-id="47dac-123">Bloquear las firmas no válidas y las que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="47dac-123">Block invalid and untrusted signatures.</span></span><br /><br /> <span data-ttu-id="47dac-124">Este valor no bloquea los paquetes sin firmar, pero bloquea las firmas generadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="47dac-124">This setting does not block unsigned packages, but blocks self-generated signatures.</span></span>|  
|<span data-ttu-id="47dac-125">3</span><span class="sxs-lookup"><span data-stu-id="47dac-125">3</span></span>|<span data-ttu-id="47dac-126">Bloquear las firmas no válidas, las que no sean de confianza y los paquetes sin firmar.</span><span class="sxs-lookup"><span data-stu-id="47dac-126">Block invalid and untrusted signatures and unsigned packages</span></span><br /><br /> <span data-ttu-id="47dac-127">Este valor también bloquea las firmas generadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="47dac-127">This setting also blocks self-generated signatures.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="47dac-128">El valor recomendado para `BlockedSignatureStates` es 3.</span><span class="sxs-lookup"><span data-stu-id="47dac-128">The recommended setting for `BlockedSignatureStates` is 3.</span></span> <span data-ttu-id="47dac-129">Este valor proporciona la protección óptima frente a paquetes sin firmar o firmas que no son válidas o no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="47dac-129">This setting provides the greatest protection against unsigned packages or signatures that are either not valid or untrusted.</span></span> <span data-ttu-id="47dac-130">No obstante, es posible que el valor recomendado no sea adecuado para todas las circunstancias.</span><span class="sxs-lookup"><span data-stu-id="47dac-130">However, the recommended setting may not be appropriate in all circumstances.</span></span> <span data-ttu-id="47dac-131">Para obtener más información sobre la firma de activos digitales, vea el tema de[introducción a la firma de código](https://go.microsoft.com/fwlink/?LinkId=51414)en MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="47dac-131">For more information about signing digital assets, see the topic, "[Introduction to Code Signing](https://go.microsoft.com/fwlink/?LinkId=51414)," in the MSDN Library.</span></span>  
  
### <a name="to-implement-a-signing-policy-for-packages"></a><span data-ttu-id="47dac-132">Para implementar una directiva de firma para paquetes</span><span class="sxs-lookup"><span data-stu-id="47dac-132">To implement a signing policy for packages</span></span>  
  
1.  <span data-ttu-id="47dac-133">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="47dac-133">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="47dac-134">En el cuadro de diálogo Ejecutar, escriba `Regedit` y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="47dac-134">In the Run dialog box, type `Regedit`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="47dac-135">Busque la clave del Registro HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span><span class="sxs-lookup"><span data-stu-id="47dac-135">Locate the registry key, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span></span>  
  
4.  <span data-ttu-id="47dac-136">Haga clic con el botón derecho en **MSDTS**, seleccione **Nuevo**y, después, haga clic en **Valor DWORD**.</span><span class="sxs-lookup"><span data-stu-id="47dac-136">Right-click **MSDTS**, point to **New**, and then click **DWORD Value**.</span></span>  
  
5.  <span data-ttu-id="47dac-137">Actualice el nombre del nuevo valor a `BlockedSignatureStates`.</span><span class="sxs-lookup"><span data-stu-id="47dac-137">Update the name of the new value to `BlockedSignatureStates`.</span></span>  
  
6.  <span data-ttu-id="47dac-138">Haga clic con el botón secundario `BlockedSignatureStates` y haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="47dac-138">Right-click `BlockedSignatureStates` and click **Modify**.</span></span>  
  
7.  <span data-ttu-id="47dac-139">En el cuadro de diálogo **Editar valor DWORD** , escriba el valor 0, 1, 2 o 3.</span><span class="sxs-lookup"><span data-stu-id="47dac-139">In the **Edit DWORD Value** dialog box, type the value 0, 1, 2, or 3.</span></span>  
  
8.  <span data-ttu-id="47dac-140">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="47dac-140">Click **OK**.</span></span>  
  
9. <span data-ttu-id="47dac-141">En el menú **Archivo** , haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="47dac-141">On the **File** menu, click **Exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47dac-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47dac-142">See Also</span></span>  
 <span data-ttu-id="47dac-143">[Información general de seguridad &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="47dac-143">[Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span></span>  
 [<span data-ttu-id="47dac-144">Identificar el origen de paquetes con firmas digitales</span><span class="sxs-lookup"><span data-stu-id="47dac-144">Identify the Source of Packages with Digital Signatures</span></span>](security/identify-the-source-of-packages-with-digital-signatures.md)  
  
  
