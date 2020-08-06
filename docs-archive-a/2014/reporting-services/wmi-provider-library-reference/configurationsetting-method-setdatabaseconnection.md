---
title: Método SetDatabaseConnection (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseConnection (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseConnection method
ms.assetid: c040aa78-92b8-41e4-9ae2-eff9fcdddc5b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b5c62777edd1fab2b0cb3babc13ab09f7bcf32a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748576"
---
# <a name="setdatabaseconnection-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="43481-102">Método SetDatabaseConnection (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="43481-102">SetDatabaseConnection Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="43481-103">Define la conexión de la base de datos del servidor de informes a una base de datos de servidor de informes concreta.</span><span class="sxs-lookup"><span data-stu-id="43481-103">Sets the report server database connection to a particular report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43481-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43481-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseConnection(Server as String, _  
    DatabaseName as string, CredentialsType as Integer, _  
    Username as String, Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void BackupEncryptionKey(string Server,   
    string DatabaseName, Int32 CredentialsType,   
    string UserName, string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43481-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43481-105">Parameters</span></span>  
 <span data-ttu-id="43481-106">*Server*</span><span class="sxs-lookup"><span data-stu-id="43481-106">*Server*</span></span>  
 <span data-ttu-id="43481-107">Nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se usa para hospedar la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="43481-107">The name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is used to host the report server database.</span></span>  
  
 <span data-ttu-id="43481-108">*DatabaseName*</span><span class="sxs-lookup"><span data-stu-id="43481-108">*DatabaseName*</span></span>  
 <span data-ttu-id="43481-109">El nombre de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="43481-109">The name of the report server database.</span></span>  
  
 <span data-ttu-id="43481-110">*CredentialsType*</span><span class="sxs-lookup"><span data-stu-id="43481-110">*CredentialsType*</span></span>  
 <span data-ttu-id="43481-111">El tipo de credenciales que se utilizará para la conexión.</span><span class="sxs-lookup"><span data-stu-id="43481-111">The type of credentials to use for the connection.</span></span> <span data-ttu-id="43481-112">Los valores pueden ser:</span><span class="sxs-lookup"><span data-stu-id="43481-112">Values can be:</span></span>  
  
-   <span data-ttu-id="43481-113">0 - Windows</span><span class="sxs-lookup"><span data-stu-id="43481-113">0 - Windows</span></span>  
  
-   <span data-ttu-id="43481-114">1 - [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43481-114">1 - [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="43481-115">2 - Servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="43481-115">2 - Windows Service</span></span>  
  
 <span data-ttu-id="43481-116">*UserName*</span><span class="sxs-lookup"><span data-stu-id="43481-116">*UserName*</span></span>  
 <span data-ttu-id="43481-117">El nombre de la cuenta utilizada para conectarse a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="43481-117">The account name used to connect to the report server database.</span></span>  
  
 <span data-ttu-id="43481-118">*Contraseña*</span><span class="sxs-lookup"><span data-stu-id="43481-118">*Password*</span></span>  
 <span data-ttu-id="43481-119">La contraseña utilizada para conectarse a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="43481-119">The password used to connect to the report server database.</span></span>  
  
 <span data-ttu-id="43481-120">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="43481-120">*HRESULT*</span></span>  
 <span data-ttu-id="43481-121">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="43481-121">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43481-122">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="43481-122">Return Value</span></span>  
 <span data-ttu-id="43481-123">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="43481-123">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="43481-124">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="43481-124">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="43481-125">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="43481-125">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43481-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="43481-126">Remarks</span></span>  
 <span data-ttu-id="43481-127">Cuando el parámetro *CredentialsType* se define en 0 (Windows), deben definirse los parámetros *UserName* y *Password* .</span><span class="sxs-lookup"><span data-stu-id="43481-127">When the *CredentialsType* parameter is set to 0 (Windows), the *UserName* and *Password* parameters must be set.</span></span> <span data-ttu-id="43481-128">El parámetro *UserName* debe tener el formato "dominio\nombre de usuario" y el valor debe representar un inicio de sesión de Windows válido.</span><span class="sxs-lookup"><span data-stu-id="43481-128">The *UserName* parameter must be in the form "domain\username", and the value must represent a valid Windows logon.</span></span>  
  
 <span data-ttu-id="43481-129">Cuando el parámetro *CredentialsType* se establece en 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), el valor pasado en el parámetro *UserName* debe cumplir los requisitos de un nombre de inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43481-129">When the *CredentialsType* parameter is set to 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), the value passed in the *UserName* parameter must conform to the requirements of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login name.</span></span>  
  
 <span data-ttu-id="43481-130">Cuando el parámetro *CredentialsType* se establece en 2 (servicio de Windows), el servidor de informes usa la seguridad integrada para conectarse a la base de datos del servidor de informes y se omiten los parámetros *UserName* y *Password* .</span><span class="sxs-lookup"><span data-stu-id="43481-130">When the *CredentialsType* parameter is set to 2 (Windows Service), the report server uses integrated security to connect to the report server database and the *UserName* and *Password* parameters are ignored.</span></span> <span data-ttu-id="43481-131">El servicio web del servidor de informes usará la cuenta [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] o una cuenta de un grupo de aplicaciones y la cuenta del servicio de Windows para acceder a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="43481-131">The Reporting Server Web service will use either the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] account or an application pool's account and the Windows service account to access the report server database.</span></span>  
  
 <span data-ttu-id="43481-132">Cuando se llama, el método SetDatabaseConnection cifra y almacena las credenciales y la información de la base de datos en el archivo de configuración del servidor de informes especificado.</span><span class="sxs-lookup"><span data-stu-id="43481-132">When called, the SetDatabaseConnection method encrypts and stores the credentials and database information in the configuration file for the specified report server.</span></span>  
  
 <span data-ttu-id="43481-133">El método SetDatabaseConnection no comprueba que el servidor de informes pueda conectarse a la base de datos del servidor de informes usando los datos especificados.</span><span class="sxs-lookup"><span data-stu-id="43481-133">The SetDatabaseConnection method does not check that the report server can connect to the report server database using the data specified.</span></span>  
  
 <span data-ttu-id="43481-134">Cuando se establece por primera vez, la propiedad ConnectionPoolSize se establece en función de los procesadores siguientes: ConnectionPoolSize = #Processors \* 75.</span><span class="sxs-lookup"><span data-stu-id="43481-134">When set for the first time, the ConnectionPoolSize property is set based on the following processors: ConnectionPoolSize = #Processors \* 75.</span></span>  
  
 <span data-ttu-id="43481-135">El método SetDatabaseConnection no concede permisos a las cuentas especificadas.</span><span class="sxs-lookup"><span data-stu-id="43481-135">The SetDatabaseConnection method does not grant permissions to the specified account(s).</span></span> <span data-ttu-id="43481-136">Debe llamar al método [GenerateDatabaseRightsScript](configurationsetting-method-generatedatabaserightsscript.md) para cada cuenta que requiera el acceso a la base de datos del servidor de informes y ejecutar el script resultante.</span><span class="sxs-lookup"><span data-stu-id="43481-136">You must call the [GenerateDatabaseRightsScript](configurationsetting-method-generatedatabaserightsscript.md) method for each account that requires access to the report server database and run the resulting script.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43481-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43481-137">Requirements</span></span>  
 <span data-ttu-id="43481-138">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43481-138">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43481-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43481-139">See Also</span></span>  
 [<span data-ttu-id="43481-140">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="43481-140">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
