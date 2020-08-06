---
title: Utilidad rskeymgmt (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], encryption
- joining report server instances [SQL Server]
- report server scale-out deployments [Reporting Services]
- cryptography [Reporting Services]
- multiple report server instances
- command prompt utilities [Reporting Services]
- report servers [Reporting Services], scale-out deployments
- encryption [Reporting Services]
- rskeymgmt utility
- scale-out deployments [Reporting Services]
ms.assetid: 53f1318d-bd2d-4c08-b19f-c8b698b5b3d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ae4bdd6656cf5b29f8fd40fcf730f49a6de8f32e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747952"
---
# <a name="rskeymgmt-utility-ssrs"></a><span data-ttu-id="b3536-102">rskeymgmt (utilidad) (SSRS)</span><span class="sxs-lookup"><span data-stu-id="b3536-102">rskeymgmt Utility (SSRS)</span></span>
  <span data-ttu-id="b3536-103">Extrae, restaura, crea y elimina la clave simétrica usada para proteger contra el acceso no autorizado los datos importantes del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3536-103">Extracts, restores, creates, and deletes the symmetric key used to protect sensitive report server data against unauthorized access.</span></span> <span data-ttu-id="b3536-104">Esta utilidad también se usa para unir instancias del servidor de informes en una implementación de ampliación horizontal.</span><span class="sxs-lookup"><span data-stu-id="b3536-104">This utility is also used to join report server instances in a scale-out deployment.</span></span> <span data-ttu-id="b3536-105">Una *implementación escalada del servidor de informes* se refiere a varias instancias del servidor de informes que comparten una sola base de datos de servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3536-105">A *report server scale-out deployment* refers to multiple report server instances that share a single report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3536-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3536-106">Syntax</span></span>  
  
```  
  
      rskeymgmt {-?}  
{-eextract}  
{-aapply}  
{-ddeleteall}  
{-srecreatekey}  
{-rremoveinstancekey}  
{-jjoinfarm}  
{-iinstance}  
{-ffile}  
{-pencryptionpassword}  
{-mremotecomputer}  
{-ninstancenameofremotecomputer}  
{-uadministratoruseraccount}  
{-vadministratorpassword}  
{-ttrace}  
```  
  
## <a name="arguments"></a><span data-ttu-id="b3536-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b3536-107">Arguments</span></span>  
 <span data-ttu-id="b3536-108">**-?**</span><span class="sxs-lookup"><span data-stu-id="b3536-108">**-?**</span></span>  
 <span data-ttu-id="b3536-109">Muestra la sintaxis de los argumentos de **rskeymgmt** .</span><span class="sxs-lookup"><span data-stu-id="b3536-109">Displays the syntax of **rskeymgmt** arguments.</span></span>  
  
 <span data-ttu-id="b3536-110">**-e**</span><span class="sxs-lookup"><span data-stu-id="b3536-110">**-e**</span></span>  
 <span data-ttu-id="b3536-111">Extrae la clave simétrica que se usa para cifrar y descifrar datos para la instancia del servidor de informes con el fin de copiarlos en un archivo.</span><span class="sxs-lookup"><span data-stu-id="b3536-111">Extracts the symmetric key used to encrypt and decrypt data for the report server instance so that you can copy it to a file.</span></span>  
  
 <span data-ttu-id="b3536-112">Este argumento no toma ningún valor.</span><span class="sxs-lookup"><span data-stu-id="b3536-112">This argument does not take a value.</span></span> <span data-ttu-id="b3536-113">Sin embargo, para completar la extracción, es necesario incluir argumentos adicionales en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b3536-113">However, you must include additional arguments on the command line to complete the extraction.</span></span> <span data-ttu-id="b3536-114">Los argumentos que debe especificar son `-f` y `-p`.</span><span class="sxs-lookup"><span data-stu-id="b3536-114">The arguments that you must specify include `-f` and`-p`.</span></span>  
  
 <span data-ttu-id="b3536-115">**-a**</span><span class="sxs-lookup"><span data-stu-id="b3536-115">**-a**</span></span>  
 <span data-ttu-id="b3536-116">Reemplaza una clave simétrica existente con una copia proporcionada en un archivo de copia de seguridad protegido mediante contraseña.</span><span class="sxs-lookup"><span data-stu-id="b3536-116">Replaces an existing symmetric key with a copy that you provide in a password protected backup file.</span></span> <span data-ttu-id="b3536-117">Todas las instancias de la clave simétrica se actualizan.</span><span class="sxs-lookup"><span data-stu-id="b3536-117">All instances of the symmetric key are updated.</span></span>  
  
 <span data-ttu-id="b3536-118">Este argumento no toma ningún valor.</span><span class="sxs-lookup"><span data-stu-id="b3536-118">This argument does not take a value.</span></span> <span data-ttu-id="b3536-119">Sin embargo, es necesario incluir argumentos adicionales en la línea de comandos para seleccionar el archivo que contiene la clave que va a aplicarse.</span><span class="sxs-lookup"><span data-stu-id="b3536-119">However, you must include additional arguments on the command line to select the file that contains the key to be applied.</span></span> <span data-ttu-id="b3536-120">Los argumentos que puede especificar son `-f` y `-p`.</span><span class="sxs-lookup"><span data-stu-id="b3536-120">The arguments that you can specify include `-f` and`-p`.</span></span>  
  
 <span data-ttu-id="b3536-121">**-d**</span><span class="sxs-lookup"><span data-stu-id="b3536-121">**-d**</span></span>  
 <span data-ttu-id="b3536-122">Elimina todas las instancias de la clave simétrica y todos los datos cifrados de una base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3536-122">Deletes all symmetric key instances and all encrypted data in a report server database.</span></span> <span data-ttu-id="b3536-123">Este argumento no toma ningún valor.</span><span class="sxs-lookup"><span data-stu-id="b3536-123">This argument does not take a value.</span></span>  
  
 `-s`  
 <span data-ttu-id="b3536-124">Genera una nueva clave simétrica y vuelve a cifrar todo el contenido cifrado utilizando la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="b3536-124">Generates a new symmetric key and re-encrypts all encrypted content using the new key.</span></span> <span data-ttu-id="b3536-125">Todas las instancias de la clave simétrica se vuelven a generar.</span><span class="sxs-lookup"><span data-stu-id="b3536-125">All instances of the symmetric key are regenerated.</span></span>  
  
 `-j`  
 <span data-ttu-id="b3536-126">Configura una instancia del servidor de informes remoto para compartir la base de datos del servidor de informes que la instancia del servidor de informes local usa.</span><span class="sxs-lookup"><span data-stu-id="b3536-126">Configures a remote report server instance to share the report server database that is used by the local report server instance.</span></span>  
  
 <span data-ttu-id="b3536-127">**-r**  *IDInstalación*</span><span class="sxs-lookup"><span data-stu-id="b3536-127">**-r**  *installationID*</span></span>  
 <span data-ttu-id="b3536-128">Quita la información de clave simétrica de una instancia de servidor de informes concreta y, por lo tanto, quita el servidor de informes de una implementación escalada.</span><span class="sxs-lookup"><span data-stu-id="b3536-128">Removes the symmetric key information for a specific report server instance, thereby removing the report server from a scale-out deployment.</span></span> <span data-ttu-id="b3536-129">*installationID* es un valor de GUID que se puede encontrar en el archivo RSReportserver.config.</span><span class="sxs-lookup"><span data-stu-id="b3536-129">The *installationID* is a GUID value that can be found in the RSReportserver.config file.</span></span>  
  
 <span data-ttu-id="b3536-130">`-f`  *filesystem*</span><span class="sxs-lookup"><span data-stu-id="b3536-130">`-f`  *file*</span></span>  
 <span data-ttu-id="b3536-131">Especifica una ruta válida al archivo que almacena una copia de seguridad de las claves simétricas.</span><span class="sxs-lookup"><span data-stu-id="b3536-131">Specifies a fully qualified path to the file that stores a backup copy of the symmetric keys.</span></span>  
  
 <span data-ttu-id="b3536-132">Para **rskeymgmt -e**, la clave simétrica se escribe en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="b3536-132">For **rskeymgmt -e**, the symmetric key is written to the file you specify.</span></span>  
  
 <span data-ttu-id="b3536-133">Para **rskeymgmt -a**, el valor de la clave simétrica almacenada en el archivo se aplica a la instancia del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3536-133">For **rskeymgmt -a**, the symmetric key value stored in the file is applied to the report server instance.</span></span>  
  
 <span data-ttu-id="b3536-134">`-p`  *contraseña*</span><span class="sxs-lookup"><span data-stu-id="b3536-134">`-p`  *password*</span></span>  
 <span data-ttu-id="b3536-135">(Se requiere para `-f`). Especifica la contraseña que se usa para realizar una copia de seguridad o para aplicar una clave simétrica.</span><span class="sxs-lookup"><span data-stu-id="b3536-135">(Required for `-f`) Specifies the password used to back up or apply a symmetric key.</span></span> <span data-ttu-id="b3536-136">Este valor no puede estar en blanco.</span><span class="sxs-lookup"><span data-stu-id="b3536-136">This value cannot be empty.</span></span>  
  
 `-i`  
 <span data-ttu-id="b3536-137">Especifica una instancia del servidor de informes local.</span><span class="sxs-lookup"><span data-stu-id="b3536-137">Specifies a local report server instance.</span></span> <span data-ttu-id="b3536-138">Este argumento es opcional si ha instalado el servidor de informes en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] predeterminada (el valor predeterminado para `-i` es MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="b3536-138">This argument is optional if you installed the report server on the default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (the default value for `-i` is MSSQLSERVER).</span></span> <span data-ttu-id="b3536-139">Si ha instalado el servidor de informes como una instancia con nombre, se requiere `-i`.</span><span class="sxs-lookup"><span data-stu-id="b3536-139">If you installed the report server as a named instance, `-i` is required.</span></span>  
  
 `-m`  
 <span data-ttu-id="b3536-140">Especifica el nombre del equipo remoto que hospeda la instancia del servidor de informes que está uniendo a la implementación de ampliación horizontal del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3536-140">Specifies the name of the remote computer that hosts the report server instance you are joining to the report server scale-out deployment.</span></span> <span data-ttu-id="b3536-141">Utilice el nombre del equipo que lo identifica en la red.</span><span class="sxs-lookup"><span data-stu-id="b3536-141">Use the name of the computer that identifies it on your network.</span></span>  
  
 `-n`  
 <span data-ttu-id="b3536-142">Especifica el nombre de la instancia del servidor de informes en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="b3536-142">Specifies the name of the report server instance on a remote computer.</span></span> <span data-ttu-id="b3536-143">Este argumento es opcional si ha instalado el servidor de informes en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] predeterminada (el valor predeterminado para `-n` es MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="b3536-143">This argument is optional if you installed the report server on the default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (the default value for `-n` is MSSQLSERVER).</span></span> <span data-ttu-id="b3536-144">Si ha instalado el servidor de informes como una instancia con nombre, se requiere `-n`.</span><span class="sxs-lookup"><span data-stu-id="b3536-144">If you installed the report server as a named instance, `-n` is required.</span></span>  
  
 <span data-ttu-id="b3536-145">`-u`  *cuentadeusuario*</span><span class="sxs-lookup"><span data-stu-id="b3536-145">`-u`  *useraccount*</span></span>  
 <span data-ttu-id="b3536-146">Especifica la cuenta de administrador del equipo remoto que está combinando con la implementación escalada.</span><span class="sxs-lookup"><span data-stu-id="b3536-146">Specifies the administrator account on the remote computer that you are joining to the scale-out deployment.</span></span> <span data-ttu-id="b3536-147">Si no se especifica una cuenta, se usan las credenciales del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="b3536-147">If an account is not specified, the credentials of the current user are used.</span></span>  
  
 <span data-ttu-id="b3536-148">`-v`  *contraseña*</span><span class="sxs-lookup"><span data-stu-id="b3536-148">`-v`  *password*</span></span>  
 <span data-ttu-id="b3536-149">(Se requiere para `-u`). Especifica la contraseña de una cuenta de administrador del equipo remoto que desea combinar con la implementación escalada.</span><span class="sxs-lookup"><span data-stu-id="b3536-149">(Required for `-u`) Specifies the password of an administrator account on the remote computer that you want to join to the scale-out deployment.</span></span>  
  
 <span data-ttu-id="b3536-150">**-t**  *seguimiento*</span><span class="sxs-lookup"><span data-stu-id="b3536-150">**-t**  *trace*</span></span>  
 <span data-ttu-id="b3536-151">Registra los mensajes de error en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b3536-151">Outputs error messages to the trace log.</span></span> <span data-ttu-id="b3536-152">Este argumento no toma ningún valor.</span><span class="sxs-lookup"><span data-stu-id="b3536-152">This argument does not take a value.</span></span> <span data-ttu-id="b3536-153">Para obtener más información, consulte [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="b3536-153">For more information, see [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="b3536-154">Permisos</span><span class="sxs-lookup"><span data-stu-id="b3536-154">Permissions</span></span>  
 <span data-ttu-id="b3536-155">Para ejecutar esta herramienta, debe ser administrador local y debe hacerlo en el equipo local que hospeda el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3536-155">You must be a local administrator to run the tool, and you must run it locally on the computer that hosts the report server.</span></span> <span data-ttu-id="b3536-156">La utilidad rskeymgmt funciona con la instancia de Windows Servidor de informes (la utilidad no puede conectar con las instancias remotas del servicio Servidor de informes de Windows y, por lo tanto, no puede usarse para administrar las claves de cifrado de una instancia del servidor de informes remoto).</span><span class="sxs-lookup"><span data-stu-id="b3536-156">The rskeymgmt utility works with the local Report Server Windows instance (the utility cannot connect to remote instances of the Report Server Windows service so it cannot be used to manage the encryption keys of a remote report server instance).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3536-157">Si usa los argumentos `-u` y `-v`, asegúrese de especificar una cuenta que tenga permisos de administrador en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="b3536-157">If you are using the `-u` and `-v` arguments, be sure to specify an account that has administrator permissions on the remote computer.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b3536-158">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b3536-158">Examples</span></span>  
 <span data-ttu-id="b3536-159">Los siguientes ejemplos muestran algunas formas de usar **rskeymgmt**.</span><span class="sxs-lookup"><span data-stu-id="b3536-159">The following examples illustrate ways of using **rskeymgmt**.</span></span> <span data-ttu-id="b3536-160">Los siguientes ejemplos muestran cómo extraer, restaurar y eliminar claves de cifrado y cómo configurar una implementación escalada del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3536-160">The following examples show how to extract, restore, and delete encryption keys, and how to configure a report server scale-out deployment.</span></span>  
  
#### <a name="extracting-encryption-keys"></a><span data-ttu-id="b3536-161">Extraer claves de cifrado</span><span class="sxs-lookup"><span data-stu-id="b3536-161">Extracting Encryption Keys</span></span>  
 <span data-ttu-id="b3536-162">Este ejemplo muestra cómo crear una copia de seguridad de la clave de cifrado y guardarla en un archivo protegido mediante contraseña en un disquete.</span><span class="sxs-lookup"><span data-stu-id="b3536-162">This example shows how to create a backup copy of the encryption key and save it to a password-protected file on a floppy disk.</span></span> <span data-ttu-id="b3536-163">Si el servidor de informes está instalado como una instancia con nombre, agregue el argumento `-i`.</span><span class="sxs-lookup"><span data-stu-id="b3536-163">If the report server is installed as a named instance, add the `-i` argument.</span></span>  
  
```  
rskeymgmt -e -f a:\backupkey\keys -p <password>  
```  
  
#### <a name="restoring-encryption-keys"></a><span data-ttu-id="b3536-164">Restaurar claves de cifrado</span><span class="sxs-lookup"><span data-stu-id="b3536-164">Restoring Encryption Keys</span></span>  
 <span data-ttu-id="b3536-165">Este ejemplo muestra cómo reemplazar la clave de cifrado.</span><span class="sxs-lookup"><span data-stu-id="b3536-165">This example shows how to replace the encryption key.</span></span> <span data-ttu-id="b3536-166">Debe especificar la ubicación de la copia de seguridad de la clave y la contraseña que desbloquea el archivo.</span><span class="sxs-lookup"><span data-stu-id="b3536-166">You must specify the location of the backup copy of the key and the password that unlocks the file.</span></span>  
  
```  
rskeymgmt -a -f a:\backupkey\keys -p <password>  
```  
  
#### <a name="deleting-encryption-keys-and-encrypted-content"></a><span data-ttu-id="b3536-167">Eliminar claves de cifrado y contenido cifrado</span><span class="sxs-lookup"><span data-stu-id="b3536-167">Deleting Encryption Keys and Encrypted Content</span></span>  
 <span data-ttu-id="b3536-168">Este ejemplo muestra cómo eliminar todas las claves de cifrado almacenadas en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3536-168">This example shows how to delete all encryption keys stored in a report server.</span></span> <span data-ttu-id="b3536-169">Si la instalación es una implementación de ampliación horizontal del servidor de informes, las claves de cifrado de todas las instancias del servidor de informes que se incluyen en la implementación se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="b3536-169">If your installation is a report server scale-out deployment, the encryption keys for all report server instances that are included in the deployment will be deleted.</span></span> <span data-ttu-id="b3536-170">Al eliminar una clave de cifrado también se eliminan los valores de cifrado existentes en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3536-170">Deleting an encryption key also deletes any existing encrypted values in the report server database.</span></span> <span data-ttu-id="b3536-171">Para más información sobre el contenido cifrado, vea [Almacenar datos cifrados del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../install-windows/ssrs-encryption-keys-store-encrypted-report-server-data.md).</span><span class="sxs-lookup"><span data-stu-id="b3536-171">For more information about encrypted content, see [Store Encrypted Report Server Data &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-store-encrypted-report-server-data.md).</span></span>  
  
```  
rskeymgmt -d  
```  
  
#### <a name="joining-a-remote-report-server-named-instance-to-a-scale-out-deployment"></a><span data-ttu-id="b3536-172">Combinar una instancia con nombre del servidor de informes remoto con una implementación de ampliación horizontal</span><span class="sxs-lookup"><span data-stu-id="b3536-172">Joining a Remote Report Server Named Instance to a Scale-out Deployment</span></span>  
 <span data-ttu-id="b3536-173">Este ejemplo muestra cómo agregar una instancia de servidor de informes que está instalada en un equipo remoto a una implementación de ampliación horizontal del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3536-173">This example shows how to add a report server instance that is installed on a remote computer to a report server scale-out deployment.</span></span> <span data-ttu-id="b3536-174">Debe ejecutar el comando en uno de los equipos que ya está configurado para usar la base de datos compartida.</span><span class="sxs-lookup"><span data-stu-id="b3536-174">You must run the command on one of the computers that is already configured to use the shared database.</span></span> <span data-ttu-id="b3536-175">Los argumentos del comando especifican la instancia del servidor de informes remoto que desea combinar con la implementación de ampliación horizontal.</span><span class="sxs-lookup"><span data-stu-id="b3536-175">The command arguments specify the remote report server instance you want to join to the scale-out deployment.</span></span>  
  
```  
rskeymgmt -j -m <remotecomputer> -n <namedreportserverinstance> -u <administratoraccount> -v <administratorpassword>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b3536-176">Implementación de ampliación horizontal del servidor de informes se refiere a un modelo de implementación en el que varias instancias del servidor de informes comparten la misma base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3536-176">A report server scale-out deployment refers to a deployment model where multiple report server instances share the same report server database.</span></span> <span data-ttu-id="b3536-177">Una base de datos del servidor de informes la puede usar cualquier instancia del servidor de informes que almacene sus claves simétricas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b3536-177">A report server database can be used by any report server instance that stores its symmetric keys in the database.</span></span> <span data-ttu-id="b3536-178">Por ejemplo, si una base de datos del servidor de informes contiene información de clave para tres instancias del servidor de informes, las tres instancias se consideran miembros de la misma implementación de ampliación horizontal.</span><span class="sxs-lookup"><span data-stu-id="b3536-178">For example, if a report server database contains key information for three report server instances, all three instances are considered to members of the same scale-out deployment.</span></span>  
  
#### <a name="joining-report-server-instances-on-the-same-computer"></a><span data-ttu-id="b3536-179">Combinar instancias del servidor de informes en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="b3536-179">Joining Report Server Instances on the Same Computer</span></span>  
 <span data-ttu-id="b3536-180">Puede crear una implementación escalada a partir de varias instancias del servidor de informes que estén instaladas en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="b3536-180">You can create a scale-out deployment from multiple report server instances that are installed on the same computer.</span></span> <span data-ttu-id="b3536-181">No establezca los argumentos `-u` y `-v` si va a combinar instancias del servidor de informes que estén instaladas en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="b3536-181">Do not set the `-u` and `-v` arguments if you are joining report server instances that are installed locally.</span></span> <span data-ttu-id="b3536-182">Los argumentos `-u` y `-v` se utilizan exclusivamente para combinar instancias desde un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="b3536-182">The `-u` and `-v` arguments are used only when you are joining an instance from a remote computer.</span></span> <span data-ttu-id="b3536-183">Si especifica los argumentos, recibirá un error que indica que las credenciales de usuario no se pueden utilizar para las conexiones locales.</span><span class="sxs-lookup"><span data-stu-id="b3536-183">If you specify the arguments, you will get the following error: "User credentials cannot be used for local connections."</span></span>  
  
 <span data-ttu-id="b3536-184">El ejemplo siguiente muestra la sintaxis para crear una implementación escalada con varias instancias locales.</span><span class="sxs-lookup"><span data-stu-id="b3536-184">The following example illustrates the syntax for creating a scale-out deployment using multiple local instances.</span></span> <span data-ttu-id="b3536-185">En este ejemplo, <`initializedinstance`> es el nombre de una instancia que ya está inicializada para usar la base de datos del servidor de informes y <`newinstance`> es el nombre de la instancia que desea agregar a la implementación:</span><span class="sxs-lookup"><span data-stu-id="b3536-185">In this example, <`initializedinstance`> is the name of an instance that is already initialized to use the report server database, and <`newinstance`> is the name of the instance that you want to add to the deployment:</span></span>  
  
```  
rskeymgmt -j -i <initializedinstance> -m <computer name> -n <newinstance>  
```  
  
#### <a name="removing-encryption-keys-for-a-single-report-server-in-a-scale-out-deployment"></a><span data-ttu-id="b3536-186">Quitar claves de cifrado para un único servidor de informes en una implementación de ampliación horizontal</span><span class="sxs-lookup"><span data-stu-id="b3536-186">Removing Encryption Keys for a Single Report Server in a Scale-out Deployment</span></span>  
 <span data-ttu-id="b3536-187">Este ejemplo muestra cómo quitar claves de cifrado de un único servidor de informes en una implementación de ampliación horizontal del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3536-187">This example shows how to remove the encryption keys for a single report server in a report server scale-out deployment.</span></span> <span data-ttu-id="b3536-188">Las claves se quitan de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b3536-188">The keys are removed from the report server database.</span></span> <span data-ttu-id="b3536-189">Cuando se han quitado las claves de la instancia del servidor de informes, esa instancia del servidor de informes ya no puede tener acceso a los datos cifrados de la base de datos, y así se quita de forma efectiva de la implementación de ampliación horizontal.</span><span class="sxs-lookup"><span data-stu-id="b3536-189">Once the keys for that report server instance are removed, that report server instance can no longer access encrypted data in the database, effectively removing it from the scale-out deployment.</span></span>  
  
 <span data-ttu-id="b3536-190">Quitar una instancia del servidor de informes de una implementación escalada le exige que especifique un identificador de instalación.</span><span class="sxs-lookup"><span data-stu-id="b3536-190">Removing a report server instance from a scale-out deployment requires you to specify an installation ID.</span></span> <span data-ttu-id="b3536-191">El identificador de instalación es un GUID almacenado en el archivo RSReportserver.config de la instancia del servidor de informes para la que desea quitar claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="b3536-191">The installation ID is a GUID stored in the RSReportserver.config file of the report server instance for which you want to remove encryption keys.</span></span> <span data-ttu-id="b3536-192">Debe ejecutar el siguiente comando en el equipo que desea quitar de la implementación de ampliación horizontal.</span><span class="sxs-lookup"><span data-stu-id="b3536-192">You must run the following command on the computer that you want to remove from the scale-out deployment.</span></span> <span data-ttu-id="b3536-193">Si el servidor de informes está instalado como una instancia con nombre, use el argumento `-i` para especificar la instancia.</span><span class="sxs-lookup"><span data-stu-id="b3536-193">If the report server is installed as a named instance, use the `-i` argument to specify the instance.</span></span> <span data-ttu-id="b3536-194">Para más información, consulte [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="b3536-194">For more information, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span>  
  
```  
rskeymgmt -r <installationID>  
```  
  
## <a name="file-location"></a><span data-ttu-id="b3536-195">Ubicación del archivo</span><span class="sxs-lookup"><span data-stu-id="b3536-195">File Location</span></span>  
 <span data-ttu-id="b3536-196">Rskeymgmt.exe se encuentra en \*\* \<*drive*> : \Archivos de Programa\microsoft SQL Server\110\Tools\Binn\*\* o en \*\* \<*drive*> : \Archivos de programa (x86) \Microsoft SQL Server\110\Tools\Binn\*\*.</span><span class="sxs-lookup"><span data-stu-id="b3536-196">Rskeymgmt.exe is located at **\<*drive*>:\Program Files\Microsoft SQL Server\110\Tools\Binn** or at **\<*drive*>:\Program Files (x86)\Microsoft SQL Server\110\Tools\Binn**.</span></span> <span data-ttu-id="b3536-197">Puede ejecutar la utilidad desde cualquier carpeta del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="b3536-197">You can run the utility from any folder on your file system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3536-198">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b3536-198">Remarks</span></span>  
 <span data-ttu-id="b3536-199">El servidor de informes cifra las credenciales almacenadas y la información de la conexión.</span><span class="sxs-lookup"><span data-stu-id="b3536-199">A report server encrypts stored credentials and connection information.</span></span> <span data-ttu-id="b3536-200">Para cifrar los datos, se utiliza una clave pública y una clave simétrica.</span><span class="sxs-lookup"><span data-stu-id="b3536-200">A public key and a symmetric key are used to encrypt data.</span></span> <span data-ttu-id="b3536-201">Para que el servidor de informes funcione, la base de datos debe tener claves válidas.</span><span class="sxs-lookup"><span data-stu-id="b3536-201">A report server database must have valid keys in order for the report server to run.</span></span> <span data-ttu-id="b3536-202">Puede usar **rskeymgmt** para realizar una copia de seguridad de las claves, eliminarlas o restaurarlas.</span><span class="sxs-lookup"><span data-stu-id="b3536-202">You can use **rskeymgmt** to back up, delete, or restore the keys.</span></span> <span data-ttu-id="b3536-203">Si las claves no se pueden restaurar, esta herramienta proporciona un método para eliminar el contenido cifrado que ya no se pueda usar.</span><span class="sxs-lookup"><span data-stu-id="b3536-203">If the keys cannot be restored, this tool provides a way to delete encrypted content that can no longer be used.</span></span>  
  
 <span data-ttu-id="b3536-204">La utilidad **rskeymgmt** se usa para administrar el conjunto de claves que se define durante la instalación o durante la inicialización.</span><span class="sxs-lookup"><span data-stu-id="b3536-204">The **rskeymgmt** utility is used to manage the key set that is defined during Setup or during initialization.</span></span> <span data-ttu-id="b3536-205">Conecta con el servicio Servidor de informes de Windows local mediante un punto final de llamada a procedimiento remoto (RPC).</span><span class="sxs-lookup"><span data-stu-id="b3536-205">It connects to the local Report Server Windows service through a Remote Procedure Call (RPC) endpoint.</span></span> <span data-ttu-id="b3536-206">El servicio Servidor de informes de Windows debe estar en ejecución para que esta utilidad funcione.</span><span class="sxs-lookup"><span data-stu-id="b3536-206">The Report Server Windows service must be running in order for this utility to work.</span></span>  
  
 <span data-ttu-id="b3536-207">Para más información sobre las claves de cifrado, vea [Configurar y administrar las claves de cifrado &#40;Administrador de configuración de SSRS&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) e [Inicializar un servidor de informes &#40;Administrador de configuración de SSRS&#41;](../install-windows/ssrs-encryption-keys-initialize-a-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="b3536-207">For more information about the encryption keys, see [Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) and [Initialize a Report Server &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-initialize-a-report-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3536-208">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3536-208">See Also</span></span>  
 <span data-ttu-id="b3536-209">[Configurar una implementación escalada del servidor de informes en modo nativo &#40;SSRS Configuration Manager&#41;](../install-windows/configure-a-native-mode-report-server-scale-out-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="b3536-209">[Configure a Native Mode Report Server Scale-Out Deployment &#40;SSRS Configuration Manager&#41;](../install-windows/configure-a-native-mode-report-server-scale-out-deployment.md) </span></span>  
 <span data-ttu-id="b3536-210">[Servidor de informes de Reporting Services &#40;modo nativo&#41;](../report-server/reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="b3536-210">[Reporting Services Report Server &#40;Native Mode&#41;](../report-server/reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="b3536-211">[Utilidades del símbolo del sistema del servidor de informes &#40;SSRS&#41;](report-server-command-prompt-utilities-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b3536-211">[Report Server Command Prompt Utilities &#40;SSRS&#41;](report-server-command-prompt-utilities-ssrs.md) </span></span>  
 [<span data-ttu-id="b3536-212">Configurar y administrar claves de cifrado &#40;Administrador de configuración de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b3536-212">Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md)  
  
  
