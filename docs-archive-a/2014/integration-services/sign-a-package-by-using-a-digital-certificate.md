---
title: Firmar un paquete mediante un certificado digital | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- digital signatures [Integration Services]
- signing packages [Integration Services]
- signatures [Integration Services]
ms.assetid: 182b115e-0fe2-4717-8dff-183f9eb6e397
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6bd0f73d609623f882e474c96a01cd3bc0274b6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751257"
---
# <a name="sign-a-package-by-using-a-digital-certificate"></a><span data-ttu-id="3f91f-102">Firmar un paquete mediante un certificado digital</span><span class="sxs-lookup"><span data-stu-id="3f91f-102">Sign a Package by Using a Digital Certificate</span></span>
  <span data-ttu-id="3f91f-103">En este tema se describe cómo firmar un paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] con un certificado digital.</span><span class="sxs-lookup"><span data-stu-id="3f91f-103">This topic describes how to sign an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package with a digital certificate.</span></span> <span data-ttu-id="3f91f-104">Puede utilizar una firma digital, junto con otros valores de configuración, para evitar que se cargue y se ejecute un paquete que no es válido.</span><span class="sxs-lookup"><span data-stu-id="3f91f-104">You can use a digital signature, together with other settings, to prevent a package that is not valid from loading and running.</span></span>  
  
 <span data-ttu-id="3f91f-105">Antes de poder firmar un paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] debe realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f91f-105">Before you can sign an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, you must do the following tasks:</span></span>  
  
-   <span data-ttu-id="3f91f-106">Crear u obtener una clave privada para asociarla al certificado y almacenarla en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="3f91f-106">Create or obtain a private key to associate with the certificate, and store this private key on the local computer.</span></span>  
  
-   <span data-ttu-id="3f91f-107">Obtener un certificado para firmar código de una entidad de certificación de confianza.</span><span class="sxs-lookup"><span data-stu-id="3f91f-107">Obtain a certificate for the purpose of code signing from a trusted certification authority.</span></span> <span data-ttu-id="3f91f-108">Puede utilizar uno de los métodos siguientes para obtener o crear un certificado:</span><span class="sxs-lookup"><span data-stu-id="3f91f-108">You can use one of the following methods to obtain or create a certificate:</span></span>  
  
    -   <span data-ttu-id="3f91f-109">Obtener un certificado de una entidad de certificación pública comercial que se dedique a emitirlos.</span><span class="sxs-lookup"><span data-stu-id="3f91f-109">Obtain a certificate from a public, commercial certification authority that issues certificates.</span></span>  
  
    -   <span data-ttu-id="3f91f-110">Obtener un certificado de un servidor de certificados que permita a una organización emitir certificados internamente.</span><span class="sxs-lookup"><span data-stu-id="3f91f-110">Obtain a certificate from a certificate server, that enables an organization to internally issue certificates.</span></span> <span data-ttu-id="3f91f-111">Tiene que agregar el certificado raíz utilizado para firmar dicho certificado al almacén **Entidades de certificación raíz de confianza** .</span><span class="sxs-lookup"><span data-stu-id="3f91f-111">You have to add the root certificate that is used to sign the certificate to the **Trusted Root Certification Authorities** store.</span></span> <span data-ttu-id="3f91f-112">Para ello, puede utilizar el complemento Certificados de [!INCLUDE[msCoName](../includes/msconame-md.md)] Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="3f91f-112">To add the root certificate, you can use the Certificates snap-in for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Management Console (MMC).</span></span> <span data-ttu-id="3f91f-113">Para obtener más información, vea el tema "[Certificate Services](https://go.microsoft.com/fwlink/?LinkId=100755)" en MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="3f91f-113">For more information, see the topic, "[Certificate Services](https://go.microsoft.com/fwlink/?LinkId=100755)," in the MSDN library.</span></span>  
  
    -   <span data-ttu-id="3f91f-114">Crear su propio certificado solo con fines de pruebas.</span><span class="sxs-lookup"><span data-stu-id="3f91f-114">Create your own certificate for testing purposes only.</span></span> <span data-ttu-id="3f91f-115">La herramienta Creación de certificados (Makecert.exe) genera certificados X.509 solo a efectos de pruebas.</span><span class="sxs-lookup"><span data-stu-id="3f91f-115">The Certificate Creation Tool (Makecert.exe) generates X.509 certificates for testing purposes.</span></span> <span data-ttu-id="3f91f-116">Para obtener más información, vea el tema "[Herramienta Creación de certificados (Makecert.exe)](https://go.microsoft.com/fwlink/?LinkId=100756)" en MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="3f91f-116">For more information, see the topic, "[Certificate Creation Tool (Makecert.exe)](https://go.microsoft.com/fwlink/?LinkId=100756)," in the MSDN Library.</span></span>  
  
     <span data-ttu-id="3f91f-117">Para obtener más información sobre los certificados, vea la Ayuda en pantalla para el complemento Certificados.</span><span class="sxs-lookup"><span data-stu-id="3f91f-117">For more information about certificates, see the online Help for the Certificates snap-in.</span></span> <span data-ttu-id="3f91f-118">Para obtener más información sobre cómo firmar activos digitales, vea el tema "[Signing and Checking Code with Authenticode](https://go.microsoft.com/fwlink/?LinkId=78100)" en MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="3f91f-118">For more information about how to sign digital assets, see the topic, "[Signing and Checking Code with Authenticode](https://go.microsoft.com/fwlink/?LinkId=78100)," in the MSDN Library.</span></span>  
  
-   <span data-ttu-id="3f91f-119">Asegurarse de que el certificado se ha habilitado para la firma de código.</span><span class="sxs-lookup"><span data-stu-id="3f91f-119">Make sure that the certificate has been enabled for code signing.</span></span> <span data-ttu-id="3f91f-120">Para determinar si un certificado está habilitado para la firma de código, revise las propiedades del certificado en el complemento Certificados.</span><span class="sxs-lookup"><span data-stu-id="3f91f-120">To determine whether a certificate is enabled for code signing, review the properties of the certificate in the Certificates snap-in.</span></span>  
  
-   <span data-ttu-id="3f91f-121">Almacenar el certificado en el almacén personal.</span><span class="sxs-lookup"><span data-stu-id="3f91f-121">Store the certificate in the Personal store.</span></span>  
  
 <span data-ttu-id="3f91f-122">Una vez completadas las tareas anteriores, puede utilizar el procedimiento siguiente para firmar un paquete.</span><span class="sxs-lookup"><span data-stu-id="3f91f-122">After you have completed the previous tasks, you can use the following procedure to sign a package.</span></span>  
  
### <a name="to-sign-a-package"></a><span data-ttu-id="3f91f-123">Para firmar un paquete</span><span class="sxs-lookup"><span data-stu-id="3f91f-123">To sign a package</span></span>  
  
1.  <span data-ttu-id="3f91f-124">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que debe firmarse.</span><span class="sxs-lookup"><span data-stu-id="3f91f-124">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to be signed.</span></span>  
  
2.  <span data-ttu-id="3f91f-125">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="3f91f-125">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3f91f-126">En el Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] , en el menú **SSIS** , haga clic en **Firma digital**.</span><span class="sxs-lookup"><span data-stu-id="3f91f-126">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, on the **SSIS** menu, click **Digital Signing**.</span></span>  
  
4.  <span data-ttu-id="3f91f-127">En el cuadro de diálogo **Firma digital** , haga clic en **Firmar**.</span><span class="sxs-lookup"><span data-stu-id="3f91f-127">In the **Digital Signing** dialog box, click **Sign**.</span></span>  
  
5.  <span data-ttu-id="3f91f-128">En el cuadro de diálogo **Seleccionar el certificado** , seleccione un certificado.</span><span class="sxs-lookup"><span data-stu-id="3f91f-128">In the **Select a Certificate** dialog box, select a certificate.</span></span>  
  
6.  <span data-ttu-id="3f91f-129">(Opcional) Haga clic en **Ver certificado**para ver la información del certificado.</span><span class="sxs-lookup"><span data-stu-id="3f91f-129">(Optional) Click **View Certificat**e to view certificate information.</span></span>  
  
7.  <span data-ttu-id="3f91f-130">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Seleccionar un certificado** .</span><span class="sxs-lookup"><span data-stu-id="3f91f-130">Click **OK** to close the **Select a Certificate** dialog box.</span></span>  
  
8.  <span data-ttu-id="3f91f-131">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Firma digital** .</span><span class="sxs-lookup"><span data-stu-id="3f91f-131">Click **OK** to close the **Digital Signing** dialog box.</span></span>  
  
9. <span data-ttu-id="3f91f-132">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="3f91f-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
     <span data-ttu-id="3f91f-133">Aunque se haya firmado el paquete, también debe configurar [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para comprobar la firma digital antes de cargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="3f91f-133">Although the package has been signed, you must now configure [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] to check or verify the digital signature before loading the package.</span></span> <span data-ttu-id="3f91f-134">Para más información, vea [Identificar el origen de paquetes con firmas digitales](security/identify-the-source-of-packages-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="3f91f-134">For more information, see [Identify the Source of Packages with Digital Signatures](security/identify-the-source-of-packages-with-digital-signatures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f91f-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f91f-135">See Also</span></span>  
 [<span data-ttu-id="3f91f-136">Información general sobre seguridad &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3f91f-136">Security Overview &#40;Integration Services&#41;</span></span>](security/security-overview-integration-services.md)  
  
  
