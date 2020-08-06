---
title: Administración extensible de claves con Azure Key Vault (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- EKM, with key vault
- TDE, EKM and key vault
- Extensible Key Management with key vault
- Key Management with key vault
- Transparent Data Encryption, using EKM and key vault
ms.assetid: 3efdc48a-8064-4ea6-a828-3fbf758ef97c
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 0e4bbc4f0c371c927988e6b91fdbf47307ad9d3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752070"
---
# <a name="extensible-key-management-using-azure-key-vault-sql-server"></a><span data-ttu-id="95656-102">Administración extensible de claves con Azure Key Vault (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="95656-102">Extensible Key Management Using Azure Key Vault (SQL Server)</span></span>
  <span data-ttu-id="95656-103">El [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] conector de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Key Vault permite [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que el cifrado aproveche el servicio de Azure Key Vault como un proveedor de [administración extensible de claves &#40;EKM&#41;](extensible-key-management-ekm.md) para proteger sus claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="95656-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Key Vault enables [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption to leverage the Azure Key Vault service as an [Extensible Key Management &#40;EKM&#41;](extensible-key-management-ekm.md) provider to protect its encryption keys.</span></span>

 <span data-ttu-id="95656-104">Este tema incluye:</span><span class="sxs-lookup"><span data-stu-id="95656-104">Included in this topic:</span></span>

-   [<span data-ttu-id="95656-105">Usos de EKM</span><span class="sxs-lookup"><span data-stu-id="95656-105">Uses of EKM</span></span>](#Uses)

-   [<span data-ttu-id="95656-106">Paso 1: configuración del Almacén de claves para su uso con SQL Server</span><span class="sxs-lookup"><span data-stu-id="95656-106">Step 1: Setting up the Key Vault for use by SQL Server</span></span>](#Step1)

-   [<span data-ttu-id="95656-107">Paso 2: instalación del conector de SQL Server</span><span class="sxs-lookup"><span data-stu-id="95656-107">Step 2: Installing the SQL Server Connector</span></span>](#Step2)

-   [<span data-ttu-id="95656-108">Paso 3: configuración de SQL Server para usar un proveedor EKM para el Almacén de claves</span><span class="sxs-lookup"><span data-stu-id="95656-108">Step 3: Configure SQL Server to use an EKM provider for the Key Vault</span></span>](#Step3)

-   [<span data-ttu-id="95656-109">Ejemplo A: cifrado de datos transparente con una clave asimétrica desde el Almacén de claves</span><span class="sxs-lookup"><span data-stu-id="95656-109">Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleA)

-   [<span data-ttu-id="95656-110">Ejemplo B: cifrado de copias de seguridad con una clave asimétrica desde el Almacén de claves</span><span class="sxs-lookup"><span data-stu-id="95656-110">Example B: Encrypting Backups by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleB)

-   [<span data-ttu-id="95656-111">Ejemplo C: cifrado de nivel de columna con una clave asimétrica desde el Almacén de claves</span><span class="sxs-lookup"><span data-stu-id="95656-111">Example C: Column Level Encryption by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleC)

##  <a name="uses-of-ekm"></a><a name="Uses"></a><span data-ttu-id="95656-112">Usos de EKM</span><span class="sxs-lookup"><span data-stu-id="95656-112">Uses of EKM</span></span>
 <span data-ttu-id="95656-113">Una organización puede utilizar el cifrado de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para proteger datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="95656-113">An organization can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption to protect sensitive data.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="95656-114">el cifrado incluye [Cifrado de datos transparente &#40;TDE&#41;](transparent-data-encryption.md), [cifrado de nivel de columna](/sql/t-sql/functions/cryptographic-functions-transact-sql) (CLE) y [cifrado de copia de seguridad](../../backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="95656-114">encryption includes [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md), [Column Level Encryption](/sql/t-sql/functions/cryptographic-functions-transact-sql) (CLE), and [Backup Encryption](../../backup-restore/backup-encryption.md).</span></span> <span data-ttu-id="95656-115">En todos estos casos, los datos se cifran con una clave de cifrado de datos simétrica.</span><span class="sxs-lookup"><span data-stu-id="95656-115">In all of these cases the data is encrypted using a symmetric data encryption key.</span></span> <span data-ttu-id="95656-116">La clave de cifrado de datos simétrica se protege, además, cifrándose con una jerarquía de claves almacenadas en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95656-116">The symmetric data encryption key is further protected by encrypting it with a hierarchy of keys stored in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="95656-117">O bien, la arquitectura del proveedor EKM permite a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proteger las claves de cifrado de datos con una clave asimétrica que se almacena fuera de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en un proveedor de servicios criptográficos externo.</span><span class="sxs-lookup"><span data-stu-id="95656-117">Alternatively, the EKM provider architecture enables [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to protect the data encryption keys by using an asymmetric key stored outside of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in an external cryptographic provider.</span></span> <span data-ttu-id="95656-118">El uso de la arquitectura de proveedor de EKM agrega un nivel de seguridad adicional y permite a las organizaciones separar la administración de claves y datos.</span><span class="sxs-lookup"><span data-stu-id="95656-118">Using EKM provider architecture adds an additional layer of security and allows organizations to separate the management of keys and data.</span></span>

 <span data-ttu-id="95656-119">El conector de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de Azure Key Vault permite a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usar el servicio de almacén de claves de alto rendimiento, alta disponibilidad y escalable como un proveedor de EKM para la protección de claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="95656-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector for Azure Key Vault lets [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] leverage the scalable, high performance, and highly available key vault service as an EKM provider for encryption key protection.</span></span> <span data-ttu-id="95656-120">El servicio de almacén de claves se puede usar con instalaciones de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en máquinas virtuales de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure y para servidores locales.</span><span class="sxs-lookup"><span data-stu-id="95656-120">The key vault service can be used with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installations on [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Virtual Machines and for on-premises servers.</span></span> <span data-ttu-id="95656-121">El servicio Almacén de claves también permite usar módulos de seguridad de hardware (HSM) supervisados y controlados estrechamente. Así, se obtiene un mayor grado de protección para las claves de cifrado asimétricas.</span><span class="sxs-lookup"><span data-stu-id="95656-121">The key vault service also provides the option to use tightly controlled and monitored Hardware Security Modules (HSMs) for a higher level of protection for asymmetric encryption keys.</span></span> <span data-ttu-id="95656-122">Para más información sobre el almacén de claves, consulte el tema sobre [Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521401).</span><span class="sxs-lookup"><span data-stu-id="95656-122">For more information about the key vault, see [Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521401).</span></span>

 <span data-ttu-id="95656-123">En la siguiente imagen se resume el flujo de procesos de EKM usando el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-123">The following image summarizes the process flow of EKM using the key vault.</span></span> <span data-ttu-id="95656-124">Los números de pasos del proceso de la imagen no de proceso de la imagen no se ofrecen con el fin de que coincidan con los números de los pasos de configuración que siguen a la imagen.</span><span class="sxs-lookup"><span data-stu-id="95656-124">The process step numbers in the image are not meant to match the setup step numbers that follow the image.</span></span>

 <span data-ttu-id="95656-125">![EKM de SQL Server con Azure Key Vault](../../../database-engine/media/ekm-using-azure-key-vault.png "EKM de SQL Server con Azure Key Vault")</span><span class="sxs-lookup"><span data-stu-id="95656-125">![SQL Server EKM using the Azure Key Vault](../../../database-engine/media/ekm-using-azure-key-vault.png "SQL Server EKM using the Azure Key Vault")</span></span>

##  <a name="step-1-set-up-the-key-vault-for-use-by-sql-server"></a><a name="Step1"></a><span data-ttu-id="95656-126">Paso 1: configurar el Key Vault para su uso por parte de SQL Server</span><span class="sxs-lookup"><span data-stu-id="95656-126">Step 1: Set up the Key Vault for use by SQL Server</span></span>
 <span data-ttu-id="95656-127">Siga estos pasos para configurar un Almacén de claves y poder usarlo con [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] para la protección de claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="95656-127">Use the following steps to set up a key vault for use with the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] for encryption key protection.</span></span> <span data-ttu-id="95656-128">Puede que la organización ya use un almacén.</span><span class="sxs-lookup"><span data-stu-id="95656-128">A vault may already be in use for the organization.</span></span> <span data-ttu-id="95656-129">Si no existe un almacén, el administrador de Azure de su organización encargado de administrar las claves de cifrado puede crear uno, generar una clave asimétrica en él y, a continuación, autorizar a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a usar la clave.</span><span class="sxs-lookup"><span data-stu-id="95656-129">When a vault does not exist, the Azure Administrator in your organization that is designated to manage encryption keys can create a vault, generate an asymmetric key in the vault, and then authorize [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use the key.</span></span> <span data-ttu-id="95656-130">Para familiarizarse con la revisión del servicio de almacén de claves, consulte [Introducción a Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402) y la referencia sobre [cmdlets de Azure Key Vault](https://docs.microsoft.com/powershell/module/azurerm.keyvault) de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95656-130">To familiarize yourself with the key vault service review [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402), and the PowerShell [Azure Key Vault Cmdlets](https://docs.microsoft.com/powershell/module/azurerm.keyvault) reference.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="95656-131">Si tiene varias suscripciones de Azure, debe usar la suscripción que contenga [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95656-131">If you have multiple Azure subscriptions, you must use the subscription that contains [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>

1.  <span data-ttu-id="95656-132">**Crear un almacén:** cree un almacén siguiendo las instrucciones de la sección **Creación de un almacén de claves** de [Introducción a Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="95656-132">**Create a vault:** Create a vault by using the instructions in the **Create a key vault** section of [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span> <span data-ttu-id="95656-133">Registre el nombre del almacén.</span><span class="sxs-lookup"><span data-stu-id="95656-133">Record the name of the vault.</span></span> <span data-ttu-id="95656-134">En este tema, se usa **ContosoKeyVault** como nombre del Almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-134">This topic uses **ContosoKeyVault** as the key vault name.</span></span>

2.  <span data-ttu-id="95656-135">**Generar una clave asimétrica en el almacén:** La clave asimétrica del almacén de claves se usa para proteger las claves de cifrado de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95656-135">**Generate an asymmetric key in the vault:** The asymmetric key in the key vault is used to protect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption keys.</span></span> <span data-ttu-id="95656-136">La parte pública de la clave asimétrica es la única que sale del almacén: el almacén no exporta nunca la parte privada.</span><span class="sxs-lookup"><span data-stu-id="95656-136">Only the public portion of the asymmetric key ever leaves the vault, the private portion is never exported by the vault.</span></span> <span data-ttu-id="95656-137">Todas las operaciones de cifrado en las que se usa la clave asimétrica se delegan al Almacén de claves de Azure y están protegidas por la seguridad del Almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-137">All cryptographic operations using the asymmetric key are delegated to the Azure Key Vault, and are protected by the key vault security.</span></span>

     <span data-ttu-id="95656-138">Hay varias maneras distintas de generar una clave asimétrica y almacenarla en el almacén.</span><span class="sxs-lookup"><span data-stu-id="95656-138">There are several ways that you can generate an asymmetric key and store it in the vault.</span></span> <span data-ttu-id="95656-139">Puede crear una clave de forma externa e importarla al almacén como un archivo.pfx.</span><span class="sxs-lookup"><span data-stu-id="95656-139">You can externally generate a key, and import the key into the vault as a .pfx file.</span></span> <span data-ttu-id="95656-140">También puede crear la clave directamente en el almacén mediante las API de almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-140">Or create the key directly in the vault by using the key vault APIs.</span></span>

     <span data-ttu-id="95656-141">El conector de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requiere que las claves asimétricas sean RSA de 2.048 bits y el nombre de la clave solo puede contener los caracteres “a-z”, “A-z”, “0-9” y “-”.</span><span class="sxs-lookup"><span data-stu-id="95656-141">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector requires the asymmetric keys to be 2048-bit RSA, and the key name can only use the characters "a-z", "A-Z", "0-9", and "-".</span></span> <span data-ttu-id="95656-142">En este documento, el nombre de la clave asimétrica es **ContosoMasterKey**.</span><span class="sxs-lookup"><span data-stu-id="95656-142">In this document the name of the asymmetric key is referred to as **ContosoMasterKey**.</span></span> <span data-ttu-id="95656-143">Reemplace este nombre por el nombre único que utilice para la clave.</span><span class="sxs-lookup"><span data-stu-id="95656-143">Replace this with the unique name you use for the key.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="95656-144">En los escenarios de producción, le recomendamos encarecidamente que importe la clave asimétrica, porque permite al administrador custodiar la clave en un sistema de custodia de clave.</span><span class="sxs-lookup"><span data-stu-id="95656-144">Importing the asymmetric key is highly recommended for production scenarios because it allows the administrator to escrow the key in a key escrow system.</span></span> <span data-ttu-id="95656-145">Si la clave asimétrica se crea en el almacén, no se puede custodiar, porque la clave privada no puede salir nunca del almacén.</span><span class="sxs-lookup"><span data-stu-id="95656-145">If the asymmetric key is created in the vault, it cannot be escrowed because the private key can never leave the vault.</span></span> <span data-ttu-id="95656-146">Las claves que se usen para proteger datos críticos se deben custodiar.</span><span class="sxs-lookup"><span data-stu-id="95656-146">Keys used to protect critical data should be escrowed.</span></span> <span data-ttu-id="95656-147">Si se pierde una clave asimétrica, los datos no podrán recuperarse nunca más.</span><span class="sxs-lookup"><span data-stu-id="95656-147">The loss of an asymmetric key will result in permanently unrecoverable data.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="95656-148">El Almacén de claves admite varias versiones de la clave que tengan el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="95656-148">The key vault supports multiple versions of the same named key.</span></span> <span data-ttu-id="95656-149">Las claves que use el conector de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no deben tener versiones ni revertirse.</span><span class="sxs-lookup"><span data-stu-id="95656-149">Keys to be used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector should not be versioned or rolled.</span></span> <span data-ttu-id="95656-150">Si el administrador quiere revertir la clave que se usa para el cifrado de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , debe crear una nueva clave con otro nombre en el almacén y usar la nueva clave para cifrar la clave de cifrado de datos (DEK).</span><span class="sxs-lookup"><span data-stu-id="95656-150">If the administrator wants to roll the key used for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption, a new key with a different name should be created in the vault and used to encrypt the DEK.</span></span>

     <span data-ttu-id="95656-151">Para más información sobre cómo importar una clave en el Almacén de claves o crear una clave en el Almacén de claves (no recomendado en entornos de producción), consulte la sección sobre **cómo agregar una clave o un secreto al Almacén de claves** de la [introducción al Almacén de claves de Azure](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="95656-151">For more information on how to import a key into the key vault or to create a key in the key vault (not recommended for a production environment), see the **Add a key or secret to the key vault** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span>

3.  <span data-ttu-id="95656-152">**Obtener entidades de servicio de Azure Active Directory para usar con SQL Server:** Cuando la organización se suscribe a un servicio en la nube de Microsoft, obtiene un Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="95656-152">**Get Azure Active Directory Service Principals to use for SQL Server:** When the organization signs up for a Microsoft cloud service, it gets an Azure Active Directory.</span></span> <span data-ttu-id="95656-153">Cree **entidades de servicio** en Azure Active Directory para que las use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (para autenticarse a sí mismo en Azure Active Directory) al acceder al Almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-153">Create **Service Principals** in the Azure Active Directory for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use (to authenticate itself to Azure Active Directory) while accessing the key vault.</span></span>

    -   <span data-ttu-id="95656-154">Una **entidad de servicio** será necesaria para que un administrador de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] acceda al almacén mientras configura [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para que use el cifrado.</span><span class="sxs-lookup"><span data-stu-id="95656-154">One **Service Principal** will be needed by a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator to access the vault while configuring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use encryption.</span></span>

    -   <span data-ttu-id="95656-155">Otra **entidad de servicio** será necesaria para que [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] acceda al almacén y pueda desempaquetar las claves utilizadas en el cifrado de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95656-155">Another **Service Principal** will be needed by the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] to access the vault for unwrapping keys used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption.</span></span>

     <span data-ttu-id="95656-156">Para más información sobre cómo registrar una aplicación y generar una entidad de servicio, consulte la sección sobre **cómo registrar una aplicación con Azure Active Directory** en la [introducción a Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="95656-156">For more information about how to register an application and generate a service principal, see the **Register an Application with Azure Active Directory** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span> <span data-ttu-id="95656-157">El proceso de registro devuelve un **Id. de aplicación** (también llamado **Id. de cliente**) y una **clave de autenticación** (también llamada **secreto**) para cada **entidad de servicio**de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="95656-157">The registration process returns an **Application ID** (also known as a **CLIENT ID**) and a **Authentication Key** (also known as a **Secret**) for each Azure Active Directory **Service Principal**.</span></span> <span data-ttu-id="95656-158">Cuando se usa en la `CREATE CREDENTIAL` instrucción, se debe quitar el guión del **ID**. de cliente.</span><span class="sxs-lookup"><span data-stu-id="95656-158">When used in the `CREATE CREDENTIAL` statement, the hyphen must be removed from the **CLIENT ID**.</span></span> <span data-ttu-id="95656-159">Regístrelos para usarlos en los siguientes scripts:</span><span class="sxs-lookup"><span data-stu-id="95656-159">Record these for use in the scripts below:</span></span>

    -   <span data-ttu-id="95656-160">**Entidad de servicio** para un inicio de sesión de **sysadmin** : **CLIENTID_sysadmin_login** y **SECRET_sysadmin_login**</span><span class="sxs-lookup"><span data-stu-id="95656-160">**Service Principal** for a **sysadmin** login: **CLIENTID_sysadmin_login** and **SECRET_sysadmin_login**</span></span>

    -   <span data-ttu-id="95656-161">**Entidad de servicio** para [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]: **CLIENTID_DBEngine** y **SECRET_DBEngine**.</span><span class="sxs-lookup"><span data-stu-id="95656-161">**Service Principal** for the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]: **CLIENTID_DBEngine** and **SECRET_DBEngine**.</span></span>

4.  <span data-ttu-id="95656-162">**Conceda permiso a las entidades de servicio para tener acceso a la Key Vault:** Las **entidades** de seguridad de **CLIENTID_sysadmin_login** y CLIENTID_DBEngineService requieren los permisos **Get**, **List**, **wrapKey**y **unwrapKey** en el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-162">**Grant Permission for the Service Principals to access the Key Vault:** Both the **CLIENTID_sysadmin_login** and **CLIENTID_DBEngineService Principals** require the **get**, **list**, **wrapKey**, and **unwrapKey** permissions in the key vault.</span></span> <span data-ttu-id="95656-163">Si tiene pensado crear las claves con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , también deberá conceder el permiso **create** en el Almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-163">If you intend to create keys through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] you also need to grant the **create** permission in key vault.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="95656-164">Los usuarios deben habilitar, al menos, las operaciones **wrapKey** y **unwrapKey** para el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-164">Users must have at least the **wrapKey** and **unwrapKey** operations for the key vault.</span></span>

     <span data-ttu-id="95656-165">Para más información sobre cómo conceder permisos en el almacén, consulte la sección sobre **cómo autorizar a la aplicación para que use la clave o el secreto** de la [introducción a Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="95656-165">For more information about granting permissions to the vault, see the **Authorize the application to use the key or secret** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span>

     <span data-ttu-id="95656-166">Vínculos a documentación del Almacén de claves de Azure</span><span class="sxs-lookup"><span data-stu-id="95656-166">Links to Azure Key Vault documentation</span></span>

    -   [<span data-ttu-id="95656-167">¿Qué es Azure Key Vault?</span><span class="sxs-lookup"><span data-stu-id="95656-167">What is Azure Key Vault?</span></span>](https://go.microsoft.com/fwlink/?LinkId=521401)

    -   [<span data-ttu-id="95656-168">Introducción al Almacén de claves de Azure</span><span class="sxs-lookup"><span data-stu-id="95656-168">Get Started with Azure Key Vault</span></span>](https://go.microsoft.com/fwlink/?LinkId=521402)

    -   <span data-ttu-id="95656-169">Referencia de [cmdlets del Almacén de claves de Azure](https://docs.microsoft.com/powershell/module/azurerm.keyvault) de PowerShell</span><span class="sxs-lookup"><span data-stu-id="95656-169">PowerShell [Azure Key Vault Cmdlets](https://docs.microsoft.com/powershell/module/azurerm.keyvault) reference</span></span>

##  <a name="step-2-install-the-sql-server-connector"></a><a name="Step2"></a><span data-ttu-id="95656-170">Paso 2: instalar el Conector de SQL Server</span><span class="sxs-lookup"><span data-stu-id="95656-170">Step 2: Install the SQL Server Connector</span></span>
 <span data-ttu-id="95656-171">El administrador del equipo de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] descarga e instala el conector de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95656-171">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector is downloaded and installed by the administrator of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="95656-172">El conector de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se puede descargar desde el [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=521700).</span><span class="sxs-lookup"><span data-stu-id="95656-172">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector is available as a download from the [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=521700).</span></span>  <span data-ttu-id="95656-173">Busque el **conector de SQL Server para Microsoft Azure Key Vault**, revise los detalles, los requisitos del sistema y las instrucciones de instalación y elija la opción de descargar el conector e iniciar la instalación con **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="95656-173">Search for **SQL Server Connector for Microsoft Azure Key Vault**, review the details, system requirements and install instructions and choose to download the connector and start the installation using **Run**.</span></span> <span data-ttu-id="95656-174">Revise la licencia, acéptela y continúe.</span><span class="sxs-lookup"><span data-stu-id="95656-174">Review the license and accept the license and continue.</span></span>

 <span data-ttu-id="95656-175">De forma predeterminada, el conector se instala en **c:\Archivos de Programa\sql Server Connector for Microsoft Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="95656-175">By default the connector is installed at **C:\Program Files\SQL Server Connector for Microsoft Azure Key Vault**.</span></span> <span data-ttu-id="95656-176">Esta ubicación se puede cambiar durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="95656-176">This location can be changed during setup.</span></span> <span data-ttu-id="95656-177">(Si la cambia, ajuste los siguientes scripts).</span><span class="sxs-lookup"><span data-stu-id="95656-177">(If changed, adjust the scripts below.)</span></span>

 <span data-ttu-id="95656-178">Al finalizar la instalación, estarán instalados en el equipo:</span><span class="sxs-lookup"><span data-stu-id="95656-178">On completing the install, the following are installed on the machine:</span></span>

-   <span data-ttu-id="95656-179">**Microsoft.AzureKeyVaultService.EKM.dll**: es la DLL del proveedor de servicios criptográficos EKM que se tiene que registrar con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con la instrucción CREATE CRYPTOGRAPHIC PROVIDER.</span><span class="sxs-lookup"><span data-stu-id="95656-179">**Microsoft.AzureKeyVaultService.EKM.dll**: This is the cryptographic EKM provider DLL that needs to be registered with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using the CREATE CRYPTOGRAPHIC PROVIDER statement.</span></span>

-   <span data-ttu-id="95656-180">**Conector de SQL Server de Azure Key Vault**: es un servicio de Windows que permite al proveedor de servicios criptográficos EKM comunicarse con Key Vault.</span><span class="sxs-lookup"><span data-stu-id="95656-180">**Azure Key Vault SQL Server Connector**: This is a Windows service that enables the cryptographic EKM provider to communicate with the key vault.</span></span>

 <span data-ttu-id="95656-181">La instalación del conector de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] también le permite descargar, si quiere, los scripts de muestra del cifrado de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95656-181">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector installation also allows you to optionally download sample scripts for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption.</span></span>

##  <a name="step-3-configure-sql-server-to-use-an-ekm-provider-for-the-key-vault"></a><a name="Step3"></a><span data-ttu-id="95656-182">Paso 3: configurar SQL Server para usar un proveedor EKM para el Key Vault</span><span class="sxs-lookup"><span data-stu-id="95656-182">Step 3: Configure SQL Server to use an EKM provider for the Key Vault</span></span>

###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="95656-183">Permisos</span><span class="sxs-lookup"><span data-stu-id="95656-183">Permissions</span></span>
 <span data-ttu-id="95656-184">Para completar este proceso, son necesarios el permiso CONTROL SERVER o la pertenencia al rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="95656-184">To complete this entire process requires CONTROL SERVER permission or membership in the **sysadmin** fixed server role.</span></span> <span data-ttu-id="95656-185">Los siguientes permisos son necesarios para realizar acciones concretas:</span><span class="sxs-lookup"><span data-stu-id="95656-185">Specific actions require the following permissions:</span></span>

-   <span data-ttu-id="95656-186">Para crear un proveedor de servicios criptográficos, son necesarios el permiso CONTROL SERVER o la pertenencia al rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="95656-186">To create a cryptographic provider, requires CONTROL SERVER permission or membership in the **sysadmin** fixed server role.</span></span>

-   <span data-ttu-id="95656-187">Para cambiar una opción de configuración y ejecutar la instrucción RECONFIGURE, debe tener el permiso ALTER SETTINGS de nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="95656-187">To change a configuration option and run the RECONFIGURE statement, you must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="95656-188">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="95656-188">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>

-   <span data-ttu-id="95656-189">Para crear una credencial, es necesario el permiso ALTER ANY CREDENTIAL.</span><span class="sxs-lookup"><span data-stu-id="95656-189">To create a credential, requires ALTER ANY CREDENTIAL permission.</span></span>

-   <span data-ttu-id="95656-190">Para agregar una credencial a un inicio de sesión, es necesario el permiso ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="95656-190">To add a credential to a login, requires ALTER ANY LOGIN permission.</span></span>

-   <span data-ttu-id="95656-191">Para crear una clave asimétrica, es necesario el permiso CREATE ASYMMETRIC KEY.</span><span class="sxs-lookup"><span data-stu-id="95656-191">To create an asymmetric key, requires CREATE ASYMMETRIC KEY permission.</span></span>

###  <a name="to-configure-sql-server-to-use-a-cryptographic-provider"></a><a name="TsqlProcedure"></a><span data-ttu-id="95656-192">Para configurar SQL Server para usar un proveedor de servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="95656-192">To configure SQL Server to use a cryptographic provider</span></span>

1.  <span data-ttu-id="95656-193">Configure [!INCLUDE[ssDE](../../../includes/ssde-md.md)] para utilizar EKM y registre (cree) el proveedor de servicios criptográficos con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95656-193">Configure the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to use EKM, and register (create) the cryptographic provider with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>

    ```sql
    -- Enable advanced options.
    USE master;
    GO

    sp_configure 'show advanced options', 1 ;
    GO
    RECONFIGURE ;
    GO
    -- Enable EKM provider
    sp_configure 'EKM provider enabled', 1 ;
    GO
    RECONFIGURE ;
    GO

    -- Create a cryptographic provider, using the SQL Server Connector
    -- which is an EKM provider for the Azure Key Vault. This example uses 
    -- the name AzureKeyVault_EKM_Prov.

    CREATE CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov 
    FROM FILE = 'C:\Program Files\SQL Server Connector for Microsoft Azure Key Vault\Microsoft.AzureKeyVaultService.EKM.dll';
    GO
    ```

2.  <span data-ttu-id="95656-194">Configure una credencial de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para un inicio de sesión de administrador de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , para utilizar el Almacén de claves con el fin de configurar y administrar escenarios de cifrado de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95656-194">Setup a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] credential for a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator login to use the key vault in order to setup and manage [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption scenarios.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="95656-195">El argumento **Identity** de `CREATE CREDENTIAL` requiere el nombre del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-195">The **IDENTITY** argument of `CREATE CREDENTIAL` requires the key vault name.</span></span> <span data-ttu-id="95656-196">El argumento **Secret** de `CREATE CREDENTIAL` requiere *\<Client ID>* (sin guiones) y *\<Secret>* se puede pasar juntos sin un espacio entre ellos.</span><span class="sxs-lookup"><span data-stu-id="95656-196">The **SECRET** argument of `CREATE CREDENTIAL` requires the *\<Client ID>* (without hyphens) and *\<Secret>* to be passed together without a space between them.</span></span>

     <span data-ttu-id="95656-197">En el ejemplo siguiente, el **identificador de cliente** ( `EF5C8E09-4D2A-4A76-9998-D93440D8115D` ) se elimina de los guiones y se escribe como la cadena `EF5C8E094D2A4A769998D93440D8115D` y el **secreto** se representa con la cadena *SECRET_sysadmin_login*.</span><span class="sxs-lookup"><span data-stu-id="95656-197">In the following example, the **Client ID** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) is stripped of the hyphens and entered as the string `EF5C8E094D2A4A769998D93440D8115D` and the **Secret** is represented by the string *SECRET_sysadmin_login*.</span></span>

    ```sql
    USE master;
    CREATE CREDENTIAL sysadmin_ekm_cred 
        WITH IDENTITY = 'ContosoKeyVault', 
        SECRET = 'EF5C8E094D2A4A769998D93440D8115DSECRET_sysadmin_login' 
    FOR CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov ;

    -- Add the credential to the SQL Server administrators domain login 
    ALTER LOGIN [<domain>/<login>]
    ADD CREDENTIAL sysadmin_ekm_cred;
    ```

     <span data-ttu-id="95656-198">Para obtener un ejemplo del uso de variables para los `CREATE CREDENTIAL` argumentos y de cómo quitar mediante programación los guiones del identificador de cliente, consulte [CREATE Credential &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="95656-198">For an example of using variables for the `CREATE CREDENTIAL` arguments and programmatically removing the hyphens from the Client ID, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>

3.  <span data-ttu-id="95656-199">Si importó una clave asimétrica como se describió anteriormente en el paso 1, sección 3, abra la clave proporcionando el nombre de la clave en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="95656-199">If you imported an asymmetric key as described earlier in step 1, section 3, open the key by providing your key name in the following example.</span></span>

    ```sql
    CREATE ASYMMETRIC KEY CONTOSO_KEY 
    FROM PROVIDER [AzureKeyVault_EKM_Prov]
    WITH PROVIDER_KEY_NAME = 'ContosoMasterKey',
    CREATION_DISPOSITION = OPEN_EXISTING;
    ```

     <span data-ttu-id="95656-200">Aunque no se recomienda para la producción (porque no se puede exportar la clave), es posible crear una clave asimétrica directamente en el almacén de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95656-200">Though not recommended for production (because the key cannot be exported), it is possible to create an asymmetric key directly in the vault from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="95656-201">Si no importó una clave anteriormente, cree una clave asimétrica en el Almacén de claves para realizar pruebas con el siguiente script.</span><span class="sxs-lookup"><span data-stu-id="95656-201">If you did not import a key earlier, then create an asymmetric key in the key vault for testing by using the following script.</span></span> <span data-ttu-id="95656-202">Ejecute el script con un inicio de sesión aprovisionado con la credencial **sysadmin_ekm_cred** .</span><span class="sxs-lookup"><span data-stu-id="95656-202">Execute the script, using a login provisioned with the **sysadmin_ekm_cred** credential.</span></span>

    ```sql
    CREATE ASYMMETRIC KEY CONTOSO_KEY 
    FROM PROVIDER [AzureKeyVault_EKM_Prov]
    WITH ALGORITHM = RSA_2048,
    PROVIDER_KEY_NAME = 'ContosoMasterKey';
    ```

> [!TIP]
>  <span data-ttu-id="95656-203">Los usuarios que reciben el error **no pueden exportar la clave pública del proveedor. Código de error de proveedor: 2053.**</span><span class="sxs-lookup"><span data-stu-id="95656-203">Users receiving the error **Cannot export public key from the provider. Provider error code: 2053.**</span></span> <span data-ttu-id="95656-204">debe comprobar sus permisos **get**, **list**, **wrapKey**y **unwrapKey** en el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-204">should check their **get**, **list**, **wrapKey**, and **unwrapKey** permissions in the key vault.</span></span>

 <span data-ttu-id="95656-205">Para obtener más información, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="95656-205">For more information, see the following:</span></span>

-   [<span data-ttu-id="95656-206">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95656-206">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)

-   [<span data-ttu-id="95656-207">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95656-207">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-cryptographic-provider-transact-sql)

-   [<span data-ttu-id="95656-208">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95656-208">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)

-   [<span data-ttu-id="95656-209">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95656-209">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)

-   [<span data-ttu-id="95656-210">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95656-210">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)

-   [<span data-ttu-id="95656-211">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95656-211">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)

## <a name="examples"></a><span data-ttu-id="95656-212">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="95656-212">Examples</span></span>

###  <a name="example-a-transparent-data-encryption-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleA"></a><span data-ttu-id="95656-213">Ejemplo A: Cifrado de datos transparente mediante el uso de una clave asimétrica del Key Vault</span><span class="sxs-lookup"><span data-stu-id="95656-213">Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="95656-214">Después de completar los pasos anteriores, cree una credencial y un inicio de sesión y cree una clave de cifrado de base de datos protegida por la clave asimétrica en el Almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-214">After completing the steps above, create a credential and a login, create a database encryption key protected by the asymmetric key in the key vault.</span></span> <span data-ttu-id="95656-215">Use la clave de cifrado de base de datos para cifrar una base de datos con cifrado de datos transparente (TDE).</span><span class="sxs-lookup"><span data-stu-id="95656-215">Use the database encryption key to encrypt a database with TDE.</span></span>

 <span data-ttu-id="95656-216">Para cifrar una base de datos, es necesario tener el permiso CONTROL en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="95656-216">To encrypt a database requires CONTROL permission on the database.</span></span>

##### <a name="to-enable-tde-using-ekm-and-the-key-vault"></a><span data-ttu-id="95656-217">Para habilitar TDE con EKM y el Almacén de claves</span><span class="sxs-lookup"><span data-stu-id="95656-217">To enable TDE using EKM and the Key Vault</span></span>

1.  <span data-ttu-id="95656-218">Cree una credencial de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para que la use [!INCLUDE[ssDE](../../../includes/ssde-md.md)] al acceder al Almacén de claves EKM mientras se carga la base de datos.</span><span class="sxs-lookup"><span data-stu-id="95656-218">Create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] credential for the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to use when accessing the key vault EKM during database load.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="95656-219">El argumento **Identity** de `CREATE CREDENTIAL` requiere el nombre del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-219">The **IDENTITY** argument of `CREATE CREDENTIAL` requires the key vault name.</span></span> <span data-ttu-id="95656-220">El argumento **Secret** de `CREATE CREDENTIAL` requiere *\<Client ID>* (sin guiones) y *\<Secret>* se puede pasar juntos sin un espacio entre ellos.</span><span class="sxs-lookup"><span data-stu-id="95656-220">The **SECRET** argument of `CREATE CREDENTIAL` requires the *\<Client ID>* (without hyphens) and *\<Secret>* to be passed together without a space between them.</span></span>

     <span data-ttu-id="95656-221">En el ejemplo siguiente, el **Id. de cliente** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) se deja sin guiones y se introduce como la cadena `EF5C8E094D2A4A769998D93440D8115D` . El **secreto** se representa con la cadena *SECRET_DBEngine*.</span><span class="sxs-lookup"><span data-stu-id="95656-221">In the following example, the **Client ID** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) is stripped of the hyphens and entered as the string `EF5C8E094D2A4A769998D93440D8115D` and the **Secret** is represented by the string *SECRET_DBEngine*.</span></span>

    ```sql
    USE master;
    CREATE CREDENTIAL Azure_EKM_TDE_cred 
        WITH IDENTITY = 'ContosoKeyVault', 
        SECRET = 'EF5C8E094D2A4A769998D93440D8115DSECRET_DBEngine' 
        FOR CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov ;
    ```

2.  <span data-ttu-id="95656-222">Cree un inicio de sesión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para que lo use [!INCLUDE[ssDE](../../../includes/ssde-md.md)] para TDE y agréguele la credencial.</span><span class="sxs-lookup"><span data-stu-id="95656-222">Create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login to be used by the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] for TDE, and add the credential to it.</span></span> <span data-ttu-id="95656-223">En este ejemplo, se utiliza la clave asimétrica CONTOSO_KEY almacenada en el Almacén de claves, que se importó o se creó anteriormente para la base de datos maestra, como se describe en el [paso 3, sección 3](#Step3) , más arriba.</span><span class="sxs-lookup"><span data-stu-id="95656-223">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier for the master database, as described in [Step 3, section 3](#Step3) above.</span></span>

    ```sql
    USE master;
    -- Create a SQL Server login associated with the asymmetric key 
    -- for the Database engine to use when it loads a database 
    -- encrypted by TDE.
    CREATE LOGIN TDE_Login 
    FROM ASYMMETRIC KEY CONTOSO_KEY;
    GO 

    -- Alter the TDE Login to add the credential for use by the 
    -- Database Engine to access the key vault
    ALTER LOGIN TDE_Login 
    ADD CREDENTIAL Azure_EKM_TDE_cred ;
    GO
    ```

3.  <span data-ttu-id="95656-224">Cree la clave de cifrado de base de datos (DEK) que se utilizará para TDE.</span><span class="sxs-lookup"><span data-stu-id="95656-224">Create the database encryption key (DEK) that will be used for TDE.</span></span> <span data-ttu-id="95656-225">La DEK puede crearse con cualquier algoritmo compatible con SQL Server y cualquier longitud de clave.</span><span class="sxs-lookup"><span data-stu-id="95656-225">The DEK can be created using any SQL Server supported algorithm or key length.</span></span> <span data-ttu-id="95656-226">La DEK estará protegida por la clave asimétrica en el Almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-226">The DEK will be protected by the asymmetric key in the key vault.</span></span>

     <span data-ttu-id="95656-227">En este ejemplo, se utiliza la clave asimétrica CONTOSO_KEY almacenada en el Almacén de claves, que se importó o se creó anteriormente, como se describe en el [paso 3, sección 3](#Step3) , más arriba.</span><span class="sxs-lookup"><span data-stu-id="95656-227">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier, as described in [Step 3, section 3](#Step3) above.</span></span>

    ```sql
    USE ContosoDatabase;
    GO

    CREATE DATABASE ENCRYPTION KEY 
    WITH ALGORITHM = AES_128 
    ENCRYPTION BY SERVER ASYMMETRIC KEY CONTOSO_KEY;
    GO

    -- Alter the database to enable transparent data encryption.
    ALTER DATABASE ContosoDatabase 
    SET ENCRYPTION ON ;
    GO
    ```

     <span data-ttu-id="95656-228">Para obtener más información, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="95656-228">For more information, see the following:</span></span>

    -   [<span data-ttu-id="95656-229">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95656-229">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)

    -   [<span data-ttu-id="95656-230">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95656-230">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)

###  <a name="example-b-encrypting-backups-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleB"></a><span data-ttu-id="95656-231">Ejemplo B: cifrado de copias de seguridad mediante una clave asimétrica desde el Key Vault</span><span class="sxs-lookup"><span data-stu-id="95656-231">Example B: Encrypting Backups by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="95656-232">Las copias de seguridad cifradas se admiten a partir de [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95656-232">Encrypted backups are supported starting with [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)].</span></span> <span data-ttu-id="95656-233">En el ejemplo siguiente, se crea y se restaura una copia de seguridad cifrada con una clave de cifrado de datos protegida por la clave asimétrica en el Almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-233">The following example creates and restores a backup encrypted a data encryption key protected by the asymmetric key in the key vault.</span></span>

```sql
USE master;
BACKUP DATABASE [DATABASE_TO_BACKUP]
TO DISK = N'[PATH TO BACKUP FILE]' 
WITH FORMAT, INIT, SKIP, NOREWIND, NOUNLOAD, 
ENCRYPTION(ALGORITHM = AES_256, SERVER ASYMMETRIC KEY = [CONTOSO_KEY]);
GO
```

 <span data-ttu-id="95656-234">Código de muestra de la restauración.</span><span class="sxs-lookup"><span data-stu-id="95656-234">Sample restore code.</span></span>

```sql
RESTORE DATABASE [DATABASE_TO_BACKUP]
FROM DISK = N'[PATH TO BACKUP FILE]' WITH FILE = 1, NOUNLOAD, REPLACE;
GO
```

 <span data-ttu-id="95656-235">Para obtener más información sobre las opciones de copia de seguridad, vea [copia de seguridad &#40;&#41;de Transact-SQL ](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="95656-235">For more information about backup options, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>

###  <a name="example-c-column-level-encryption-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleC"></a><span data-ttu-id="95656-236">Ejemplo C: cifrado de nivel de columna con una clave asimétrica desde el Key Vault</span><span class="sxs-lookup"><span data-stu-id="95656-236">Example C: Column Level Encryption by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="95656-237">En el ejemplo siguiente, se crea una clave simétrica protegida por la clave asimétrica en el Almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="95656-237">The following example creates a symmetric key protected by the asymmetric key in the key vault.</span></span> <span data-ttu-id="95656-238">Luego, se usa la clave simétrica para cifrar los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="95656-238">Then the symmetric key is used to encrypt data in the database.</span></span>

 <span data-ttu-id="95656-239">En este ejemplo, se utiliza la clave asimétrica CONTOSO_KEY almacenada en el Almacén de claves, que se importó o se creó anteriormente, como se describe en el [paso 3, sección 3](#Step3) , más arriba.</span><span class="sxs-lookup"><span data-stu-id="95656-239">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier, as described in [Step 3, section 3](#Step3) above.</span></span> <span data-ttu-id="95656-240">Para utilizar esta clave asimétrica en la base de datos `ContosoDatabase` , debe ejecutar de nuevo la instrucción CREATE ASYMMETRIC KEY para proporcionar a la base de datos `ContosoDatabase` una referencia a la clave.</span><span class="sxs-lookup"><span data-stu-id="95656-240">To use this asymmetric key in the `ContosoDatabase` database, you must execute the CREATE ASYMMETRIC KEY statement again, to provide the `ContosoDatabase` database with a reference to the key.</span></span>

```sql
USE [ContosoDatabase];
GO

-- Create a reference to the key in the key vault
CREATE ASYMMETRIC KEY CONTOSO_KEY 
FROM PROVIDER [AzureKeyVault_EKM_Prov]
WITH PROVIDER_KEY_NAME = 'ContosoMasterKey',
CREATION_DISPOSITION = OPEN_EXISTING;

-- Create the data encryption key.
-- The data encryption key can be created using any SQL Server 
-- supported algorithm or key length.
-- The DEK will be protected by the asymmetric key in the key vault

CREATE SYMMETRIC KEY DATA_ENCRYPTION_KEY
    WITH ALGORITHM=AES_256
    ENCRYPTION BY ASYMMETRIC KEY CONTOSO_KEY;

DECLARE @DATA VARBINARY(MAX);

--Open the symmetric key for use in this session
OPEN SYMMETRIC KEY DATA_ENCRYPTION_KEY 
DECRYPTION BY ASYMMETRIC KEY CONTOSO_KEY;

--Encrypt syntax
SELECT @DATA = ENCRYPTBYKEY(KEY_GUID('DATA_ENCRYPTION_KEY'), CONVERT(VARBINARY,'Plain text data to encrypt'));

-- Decrypt syntax
SELECT CONVERT(VARCHAR, DECRYPTBYKEY(@DATA));

--Close the symmetric key
CLOSE SYMMETRIC KEY DATA_ENCRYPTION_KEY;
```

## <a name="see-also"></a><span data-ttu-id="95656-241">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95656-241">See Also</span></span>
 <span data-ttu-id="95656-242">[Crear un proveedor de servicios criptográficos &#40;Transact-sql&#41;](/sql/t-sql/statements/create-cryptographic-provider-transact-sql) [crear credencial &#40;transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [crear una clave asimétrica &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [crear una clave simétrica &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-symmetric-key-transact-sql) [Administración extensible de claves &#40;EKM&#41;](extensible-key-management-ekm.md) [Habilitar TDE con](enable-tde-on-sql-server-using-ekm.md) el [cifrado de copia de seguridad](../../backup-restore/backup-encryption.md) EKM [crear una copia de seguridad cifrada](../../backup-restore/create-an-encrypted-backup.md)</span><span class="sxs-lookup"><span data-stu-id="95656-242">[CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-cryptographic-provider-transact-sql) [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-symmetric-key-transact-sql) [Extensible Key Management &#40;EKM&#41;](extensible-key-management-ekm.md) [Enable TDE Using EKM](enable-tde-on-sql-server-using-ekm.md) [Backup Encryption](../../backup-restore/backup-encryption.md) [Create an Encrypted Backup](../../backup-restore/create-an-encrypted-backup.md)</span></span>
