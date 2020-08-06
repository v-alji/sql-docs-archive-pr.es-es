---
title: Administrador de conexiones de Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSCM.F1
- SQL11.DTS.DESIGNER.AFPADLSCM.F1
ms.assetid: 7f1323f9-9dc3-4378-9c70-bbc65bfeabfd
author: yualan
ms.author: chugu
ms.openlocfilehash: 1ab6e90aad6472cc10bbb12cf4ca17def501bf00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749409"
---
# <a name="azure-data-lake-store-connection-manager"></a><span data-ttu-id="7ec29-102">Administrador de conexiones de Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="7ec29-102">Azure Data Lake Store Connection Manager</span></span>
  <span data-ttu-id="7ec29-103">El **administrador de conexiones de Azure Data Lake Store** habilita un paquete SSIS para conectarse a un servicio de Azure Data Lake Store mediante dos tipos de autenticación: la identidad de usuario de Azure AD y la identidad de servicio de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7ec29-103">The **Azure Data Lake Store connection manager** enables an SSIS package to connect to an Azure Data Lake Store service through two authentication types: Azure AD User Identity and Azure AD Service Identity.</span></span>  

## <a name="configure-the-azure-data-lake-store-connection-manager"></a><span data-ttu-id="7ec29-104">Configurar el administrador de conexiones de Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="7ec29-104">Configure the Azure Data Lake Store Connection Manager</span></span> 
  
1.  <span data-ttu-id="7ec29-105">En el cuadro de diálogo **Agregar administrador de conexiones SSIS** , seleccione **AzureDataLake**y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7ec29-105">In the **Add SSIS Connection Manager** dialog box, select **AzureDataLake**, and click **Add**.</span></span>   
  
2.  <span data-ttu-id="7ec29-106">En el cuadro de diálogo Editor de administrador de conexiones de AzureDataLake, escriba la dirección URL de Azure Data Lake Store en el campo **Host ADLS** .</span><span class="sxs-lookup"><span data-stu-id="7ec29-106">In the Azure Data Lake Store Connection Manager Editor dialog box, type in the Azure Data Lake Store host URL in **ADLS Host** field.</span></span> <span data-ttu-id="7ec29-107">Por ejemplo: https: \/ /Test.azuredatalakestore.net o test.azuredatalakestore.net.</span><span class="sxs-lookup"><span data-stu-id="7ec29-107">For example: https:\//test.azuredatalakestore.net or test.azuredatalakestore.net.</span></span>
  
3.  <span data-ttu-id="7ec29-108">Elija el tipo de autenticación correspondiente para tener acceso a datos de Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="7ec29-108">Choose corresponding authentication type to access Azure Data Lake Store data.</span></span>

    1.  <span data-ttu-id="7ec29-109">Si ha seleccionado la opción de autenticación **Identidad de usuario de Azure AD** , realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ec29-109">If you selected **Azure AD User Identity** authentication option, do the following:</span></span>

        1. <span data-ttu-id="7ec29-110">Especifique los valores para los campos **Nombre de usuario** y **Contraseña** .</span><span class="sxs-lookup"><span data-stu-id="7ec29-110">Specify values for the **User Name** and **Password** field.</span></span> 
    
        2. <span data-ttu-id="7ec29-111">Haga clic en el botón **Probar conexión** para probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="7ec29-111">Click **Test Connection** button to test the connection.</span></span> <span data-ttu-id="7ec29-112">Si usted y el administrador de inquilinos no otorgan antes su consentimiento a SSIS para tener acceso a los datos de Azure Data Lake Store, deberá hacer clic en el botón **Aceptar** para permitir que SSIS tenga acceso a los datos de Azure Data Lake Store en el cuadro de diálogo emergente.</span><span class="sxs-lookup"><span data-stu-id="7ec29-112">If you and your tenant administrator didn't consent SSIS to access your Azure Data Lake Store data before, you need click **Accept** button to consent SSIS to access your Azure Data Lake Store data in the pop out dialog.</span></span> <span data-ttu-id="7ec29-113">Para obtener más información sobre esta experiencia del consentimiento, consulte [Integración de aplicaciones con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration#integrating-applications-with-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="7ec29-113">For more information about this consent experience, see [Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration#integrating-applications-with-azure-ad).</span></span>
    
        > [!NOTE] 
        > <span data-ttu-id="7ec29-114">Para la opción de autenticación Identidad de usuario de Azure AD, NO se admiten cuentas de Microsoft ni Multi-Factor Authentication.</span><span class="sxs-lookup"><span data-stu-id="7ec29-114">For Azure AD User Identity authentication option, multi-factor authentication and Microsoft account is NOT supported.</span></span>
    
    2.  <span data-ttu-id="7ec29-115">Si ha seleccionado la opción de autenticación **Identidad de servicio de Azure AD** , realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ec29-115">If you selected **Azure AD Service Identity** authentication option, do the following:</span></span>
        1. <span data-ttu-id="7ec29-116">Cree una aplicación de AAD y la entidad de servicio que pueden tener acceso a recursos de Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="7ec29-116">Create an AAD application and service principal that can access Azure Data Lake resources.</span></span>
    
        2. <span data-ttu-id="7ec29-117">Asigne a esta aplicación de AAD los permisos correspondientes para tener acceso a los recursos de Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="7ec29-117">Assign this AAD application corresponding permissions to access your Azure Data Lake resources.</span></span> <span data-ttu-id="7ec29-118">Para obtener más información sobre esta opción de autenticación, consulte [Use portal to create Active Directory application and service principal that can access resources](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal)(Utilizar el portal para crear una aplicación de Active Directory y una entidad de servicio que puedan tener acceso a los recursos).</span><span class="sxs-lookup"><span data-stu-id="7ec29-118">For more information about this authentication option, see [Use portal to create Active Directory application and service principal that can access resources](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span></span>
    
        3. <span data-ttu-id="7ec29-119">Especifique los valores para los campos **Id. de cliente**, **Clave secreta** y **Nombre de inquilino** .</span><span class="sxs-lookup"><span data-stu-id="7ec29-119">Specify values for **Client Id**, **Secret Key** and **Tenant Name** field.</span></span>
    
        4. <span data-ttu-id="7ec29-120">Haga clic en el botón **Probar conexión** para probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="7ec29-120">Click **Test Connection** button to test the connection.</span></span>  
  
4.  <span data-ttu-id="7ec29-121">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7ec29-121">Click **OK** to close the dialog box.</span></span>  
  
    <span data-ttu-id="7ec29-122">Puede ver las propiedades del Administrador de conexiones que creó en la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="7ec29-122">You can see the properties of the connection manager you created in the **Properties** window.</span></span>  
  
  
