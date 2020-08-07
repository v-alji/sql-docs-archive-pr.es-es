---
title: Habilitar y deshabilitar espacio seguro para RDL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d5619e9f-ec5b-4376-9b34-1f74de6fade7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7af1477751093862c99d00978278315e600511e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747485"
---
# <a name="enable-and-disable-rdl-sandboxing"></a><span data-ttu-id="52267-102">Habilitar y deshabilitar el espacio seguro para RDL</span><span class="sxs-lookup"><span data-stu-id="52267-102">Enable and Disable RDL Sandboxing</span></span>
  <span data-ttu-id="52267-103">La característica de espacio aislado del lenguaje RDL (Report Definition Language) permite detectar y restringir el uso de tipos específicos de uso de recursos por parte de inquilinos individuales en un entorno donde varios inquilinos usan una única granja web de servidores de informes.</span><span class="sxs-lookup"><span data-stu-id="52267-103">The RDL (Report Definition Language) Sandboxing feature lets you detect and restrict the usage of specific types of resources, by individual tenants, in an environment of multiple tenants that use a single web farm of report servers.</span></span> <span data-ttu-id="52267-104">Un ejemplo de esto es un escenario de servicios de hospedaje en el que podría mantener una única granja web de servidores de informes que utilicen varios inquilinos, y quizás compañías diferentes.</span><span class="sxs-lookup"><span data-stu-id="52267-104">An example of this is a hosting services scenario where you might maintain a single web farm of report servers that are used by multiple tenants, and perhaps different companies.</span></span> <span data-ttu-id="52267-105">Como administrador del servidor de informes, puede habilitar esta característica para alcanzar los siguientes objetivos:</span><span class="sxs-lookup"><span data-stu-id="52267-105">As a report server administrator, you can enable this feature to help achieve the following objectives:</span></span>  
  
-   <span data-ttu-id="52267-106">Restringir los tamaños de recursos externos.</span><span class="sxs-lookup"><span data-stu-id="52267-106">Restrict external resource sizes.</span></span> <span data-ttu-id="52267-107">Entre los recursos externos se incluyen imágenes, archivos .xslt y datos de mapas.</span><span class="sxs-lookup"><span data-stu-id="52267-107">External resources include images, .xslt files, and map data.</span></span>  
  
-   <span data-ttu-id="52267-108">En el tiempo de publicación del informe, limitar los tipos y los miembros que se usan en el texto de expresión.</span><span class="sxs-lookup"><span data-stu-id="52267-108">At report publish time, limit types and members that are used in expression text.</span></span>  
  
-   <span data-ttu-id="52267-109">En el tiempo de procesamiento del informe, limitar la longitud del texto y el texto del valor de devolución de las expresiones.</span><span class="sxs-lookup"><span data-stu-id="52267-109">At report processing time, limit the length of the text and the size of the return value for expressions.</span></span>  
  
 <span data-ttu-id="52267-110">Cuando se habilita el espacio aislado de RDL, se deshabilitan las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="52267-110">When RDL Sandboxing is enabled, the following features are disabled:</span></span>  
  
-   <span data-ttu-id="52267-111">Código personalizado en el **\<Code>** elemento de una definición de informe.</span><span class="sxs-lookup"><span data-stu-id="52267-111">Custom code in the **\<Code>** element of a report definition.</span></span>  
  
-   <span data-ttu-id="52267-112">Modo de compatibilidad con versiones anteriores de RDL para los elementos de informe personalizados de [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52267-112">RDL backward compatibility mode for [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] custom report items.</span></span>  
  
-   <span data-ttu-id="52267-113">Parámetros con nombre en expresiones.</span><span class="sxs-lookup"><span data-stu-id="52267-113">Named parameters in expressions.</span></span>  
  
 <span data-ttu-id="52267-114">En este tema se describe cada elemento del `RDLSandboxing` elemento <> en el archivo RSReportServer.Config.</span><span class="sxs-lookup"><span data-stu-id="52267-114">This topic describes each element in the <`RDLSandboxing`> element in the RSReportServer.Config file.</span></span> <span data-ttu-id="52267-115">Para más información sobre cómo modificar este archivo, vea [Modificar un archivo de configuración de Reporting Services &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="52267-115">For more information about how to modify this file, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span> <span data-ttu-id="52267-116">Un registro de seguimiento del servidor guarda la actividad relacionada con la característica de espacio aislado de RDL.</span><span class="sxs-lookup"><span data-stu-id="52267-116">A server trace log records activity related to the RDL Sandboxing feature.</span></span> <span data-ttu-id="52267-117">Para más información sobre los registros de seguimiento, vea [Registro de seguimiento del servicio del servidor de informes](report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="52267-117">For more information about trace logs, see [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span></span>  
  
## <a name="example-configuration"></a><span data-ttu-id="52267-118">Configuración de ejemplo</span><span class="sxs-lookup"><span data-stu-id="52267-118">Example Configuration</span></span>  
 <span data-ttu-id="52267-119">En el ejemplo siguiente se muestra la configuración y los valores de ejemplo para el `RDLSandboxing` elemento <> en el archivo RSReportServer.Config.</span><span class="sxs-lookup"><span data-stu-id="52267-119">The following example shows the settings and example values for the <`RDLSandboxing`> element in the RSReportServer.Config file.</span></span>  
  
```  
<RDLSandboxing>  
   <MaxExpressionLength>5000</MaxExpressionLength>  
   <MaxResourceSize>5000</MaxResourceSize>  
   <MaxStringResultLength>3000</MaxStringResultLength>  
   <MaxArrayResultLength>250</MaxArrayResultLength>  
   <Types>  
      <Allow Namespace="System.Drawing" AllowNew="True">Bitmap</Allow>  
      <Allow Namespace="TypeConverters.Custom" AllowNew="True">*</Allow>  
   </Types>  
   <Members>  
      <Deny>Format</Deny>  
      <Deny>StrDup</Deny>  
   </Members>  
</RDLSandboxing>  
```  
  
## <a name="configuration-settings"></a><span data-ttu-id="52267-120">Valores de configuración</span><span class="sxs-lookup"><span data-stu-id="52267-120">Configuration Settings</span></span>  
 <span data-ttu-id="52267-121">La siguiente tabla proporciona información acerca de los parámetros de configuración.</span><span class="sxs-lookup"><span data-stu-id="52267-121">The following table provides information about configuration settings.</span></span> <span data-ttu-id="52267-122">Los parámetros se presentan en el orden en que aparecen en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="52267-122">Settings are presented in the order in which they appear in the configuration file.</span></span>  
  
|<span data-ttu-id="52267-123">Configuración</span><span class="sxs-lookup"><span data-stu-id="52267-123">Setting</span></span>|<span data-ttu-id="52267-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="52267-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52267-125">**MaxExpressionLength**</span><span class="sxs-lookup"><span data-stu-id="52267-125">**MaxExpressionLength**</span></span>|<span data-ttu-id="52267-126">Número máximo de caracteres permitido en expresiones RDL.</span><span class="sxs-lookup"><span data-stu-id="52267-126">Maximum number of characters allowed in RDL expressions.</span></span><br /><br /> <span data-ttu-id="52267-127">Valor predeterminado: 1000</span><span class="sxs-lookup"><span data-stu-id="52267-127">Default: 1000</span></span>|  
|<span data-ttu-id="52267-128">**MaxResourceSize**</span><span class="sxs-lookup"><span data-stu-id="52267-128">**MaxResourceSize**</span></span>|<span data-ttu-id="52267-129">Número máximo de KB permitido para un recurso externo.</span><span class="sxs-lookup"><span data-stu-id="52267-129">Maximum number of KB allowed for an external resource.</span></span><br /><br /> <span data-ttu-id="52267-130">Valor predeterminado: 100</span><span class="sxs-lookup"><span data-stu-id="52267-130">Default: 100</span></span>|  
|<span data-ttu-id="52267-131">**MaxStringResultLength**</span><span class="sxs-lookup"><span data-stu-id="52267-131">**MaxStringResultLength**</span></span>|<span data-ttu-id="52267-132">Número máximo de caracteres permitido en un valor de devolución para una expresión RDL.</span><span class="sxs-lookup"><span data-stu-id="52267-132">Maximum number of characters allowed in a return value for an RDL expression.</span></span><br /><br /> <span data-ttu-id="52267-133">Valor predeterminado: 1000</span><span class="sxs-lookup"><span data-stu-id="52267-133">Default: 1000</span></span>|  
|<span data-ttu-id="52267-134">**MaxArrayResultLength**</span><span class="sxs-lookup"><span data-stu-id="52267-134">**MaxArrayResultLength**</span></span>|<span data-ttu-id="52267-135">Número máximo de elementos permitido en un valor de devolución de matriz para una expresión RDL.</span><span class="sxs-lookup"><span data-stu-id="52267-135">Maximum number of items allowed in an array return value for an RDL expression.</span></span><br /><br /> <span data-ttu-id="52267-136">Valor predeterminado: 100</span><span class="sxs-lookup"><span data-stu-id="52267-136">Default: 100</span></span>|  
|<span data-ttu-id="52267-137">**Tipos**</span><span class="sxs-lookup"><span data-stu-id="52267-137">**Types**</span></span>|<span data-ttu-id="52267-138">Lista de los miembros que se permitirán en las expresiones RDL.</span><span class="sxs-lookup"><span data-stu-id="52267-138">The list of members to allow within RDL expressions.</span></span>|  
|<span data-ttu-id="52267-139">**Permitir**</span><span class="sxs-lookup"><span data-stu-id="52267-139">**Allow**</span></span>|<span data-ttu-id="52267-140">Tipo o conjunto de tipos que se permitirán en las expresiones RDL.</span><span class="sxs-lookup"><span data-stu-id="52267-140">A type or set of types to allow in RDL expressions.</span></span>|  
|<span data-ttu-id="52267-141">**Espacio de nombres**</span><span class="sxs-lookup"><span data-stu-id="52267-141">**Namespace**</span></span>|<span data-ttu-id="52267-142">Atributo de **Allow** que es el espacio de nombres que contiene uno o varios tipos que se aplican a Value.</span><span class="sxs-lookup"><span data-stu-id="52267-142">Attribute for **Allow** that is the namespace that contains one or more types that apply to Value.</span></span> <span data-ttu-id="52267-143">Esta propiedad no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="52267-143">This property is case-insensitive.</span></span>|  
|`AllowNew`|<span data-ttu-id="52267-144">Atributo booleano de **Allow** que controla si se pueden crear nuevas instancias del tipo en expresiones RDL o en un **\<Class>** elemento RDL.</span><span class="sxs-lookup"><span data-stu-id="52267-144">Boolean attribute for **Allow** that controls whether new instances of the type are allowed to be created in RDL expressions or in an RDL **\<Class>** element.</span></span><br /><br /> <span data-ttu-id="52267-145">Nota: cuando `RDLSandboxing` está habilitado, no se pueden crear nuevas matrices en expresiones RDL, independientemente de la configuración de `AllowNew` .</span><span class="sxs-lookup"><span data-stu-id="52267-145">Note: When `RDLSandboxing` is enabled, new arrays cannot be created in RDL expressions, regardless of the setting of `AllowNew`.</span></span>|  
|<span data-ttu-id="52267-146">**Valor**</span><span class="sxs-lookup"><span data-stu-id="52267-146">**Value**</span></span>|<span data-ttu-id="52267-147">Valor de **Allow** que es el nombre del tipo que se permitirá en las expresiones RDL.</span><span class="sxs-lookup"><span data-stu-id="52267-147">Value for **Allow** that is the name of the type to allow in RDL expressions.</span></span> <span data-ttu-id="52267-148">El valor **\*** indica que se permiten todos los tipos del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="52267-148">The value **\*** indicates that all types in the namespace are allowed.</span></span> <span data-ttu-id="52267-149">Esta propiedad no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="52267-149">This property is case-insensitive.</span></span>|  
|<span data-ttu-id="52267-150">**Miembros**</span><span class="sxs-lookup"><span data-stu-id="52267-150">**Members**</span></span>|<span data-ttu-id="52267-151">Para la lista de tipos que se incluyen en el **\<Types>** elemento, la lista de nombres de miembro que no se permiten en las expresiones RDL.</span><span class="sxs-lookup"><span data-stu-id="52267-151">For the list of types that are include in the **\<Types>** element, the list of member names that are not allowed in RDL expressions.</span></span>|  
|<span data-ttu-id="52267-152">**Denegar**</span><span class="sxs-lookup"><span data-stu-id="52267-152">**Deny**</span></span>|<span data-ttu-id="52267-153">Nombre de un miembro que no se permite en expresiones RDL.</span><span class="sxs-lookup"><span data-stu-id="52267-153">The name of a member that is not allowed in RDL expressions.</span></span> <span data-ttu-id="52267-154">Esta propiedad no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="52267-154">This property is case-insensitive.</span></span><br /><br /> <span data-ttu-id="52267-155">Nota: Cuando se especifica **Deny** para un miembro, no se permite ningún miembro con este nombre para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="52267-155">Note: When **Deny** is specified for a member, all members with this name for all types are not allowed.</span></span>|  
  
## <a name="working-with-expressions-when-rdl-sandboxing-is-enabled"></a><span data-ttu-id="52267-156">Trabajar con expresiones cuando se habilita el espacio aislado de RDL</span><span class="sxs-lookup"><span data-stu-id="52267-156">Working with Expressions when RDL Sandboxing is Enabled</span></span>  
 <span data-ttu-id="52267-157">Puede modificar la característica de espacio aislado de RDL para administrar los recursos que usa una explorador de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="52267-157">You can modify the RDL Sandboxing feature to help manage the resources that are used by an expression in the following ways:</span></span>  
  
-   <span data-ttu-id="52267-158">Restringir el número de caracteres que se usa para una expresión.</span><span class="sxs-lookup"><span data-stu-id="52267-158">Restrict the number of characters that are used for an expression.</span></span>  
  
-   <span data-ttu-id="52267-159">Restringir el tamaño del resultado devuelto por una expresión.</span><span class="sxs-lookup"><span data-stu-id="52267-159">Restrict the size of the result returned by an expression.</span></span>  
  
-   <span data-ttu-id="52267-160">Permitir una lista específica de tipos que se pueden usar en una expresión.</span><span class="sxs-lookup"><span data-stu-id="52267-160">Allow a specific list of types that can be used in an expression.</span></span>  
  
-   <span data-ttu-id="52267-161">Restringir la lista de miembros por nombre para la lista de tipos permitidos que se pueden usar en una expresión.</span><span class="sxs-lookup"><span data-stu-id="52267-161">Restrict the list of members by name for the list of allowed types that can be used in an expression.</span></span>  
  
-   <span data-ttu-id="52267-162">La característica de espacio aislado de RDL permite crear una lista de tipos aprobados y una lista de miembros denegados.</span><span class="sxs-lookup"><span data-stu-id="52267-162">The RDL Sandboxing feature enables you to create a list of approved types and a list of denied members.</span></span> <span data-ttu-id="52267-163">La lista de tipos aprobados se denomina lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="52267-163">The list of approved types is called an allow list.</span></span> <span data-ttu-id="52267-164">La lista de miembros denegados se denomina lista de bloqueados.</span><span class="sxs-lookup"><span data-stu-id="52267-164">The list of denied members is called a block list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52267-165">En la definición de informe, un equipo no puede conocer el tipo de cada instancia de una referencia de expresión.</span><span class="sxs-lookup"><span data-stu-id="52267-165">In the report definition, a computer cannot know the type of each instances of an expression reference.</span></span> <span data-ttu-id="52267-166">Al agregar un miembro a la lista de bloqueados, se están denegando todos los miembros de ese nombre en todos los tipos de la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="52267-166">When you add a member to the block list, you are denying all members of that name across all types in the allow list.</span></span>  
  
 <span data-ttu-id="52267-167">Los resultados de la expresión RDL se comprueban en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="52267-167">RDL expression results are verified at run time.</span></span> <span data-ttu-id="52267-168">Las expresiones RDL se comprueban en la definición de informe cuando se publica el informe.</span><span class="sxs-lookup"><span data-stu-id="52267-168">RDL expressions are verified in the report definition when the report is published.</span></span> <span data-ttu-id="52267-169">Supervise el registro de seguimiento del servidor de informes por si se han producido infracciones.</span><span class="sxs-lookup"><span data-stu-id="52267-169">Monitor the report server trace log for violations.</span></span> <span data-ttu-id="52267-170">Para obtener más información, consulte [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="52267-170">For more information, see [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span></span>  
  
### <a name="working-with-types"></a><span data-ttu-id="52267-171">Trabajar con tipos</span><span class="sxs-lookup"><span data-stu-id="52267-171">Working with Types</span></span>  
 <span data-ttu-id="52267-172">Al agregar un tipo a la lista de permitidos, se controlan los siguientes puntos de entrada para obtener acceso a las expresiones RDL:</span><span class="sxs-lookup"><span data-stu-id="52267-172">When you add a type to the allow list, you are controlling the following entry points to access RDL expressions:</span></span>  
  
-   <span data-ttu-id="52267-173">Miembros estáticos de un tipo.</span><span class="sxs-lookup"><span data-stu-id="52267-173">Static members of a type.</span></span>  
  
-   <span data-ttu-id="52267-174">El [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] `New` método.</span><span class="sxs-lookup"><span data-stu-id="52267-174">The [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] `New` method.</span></span>  
  
-   <span data-ttu-id="52267-175">**\<Classes>** Elemento de la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="52267-175">The **\<Classes>** element in the report definition.</span></span>  
  
-   <span data-ttu-id="52267-176">Miembros que ha agregado a la lista de bloqueados para un tipo de la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="52267-176">Members that you have added to the block list for a type in the allow list.</span></span>  
  
 <span data-ttu-id="52267-177">La lista de permitidos no controla los siguientes puntos de entrada:</span><span class="sxs-lookup"><span data-stu-id="52267-177">The allow list does not control the following entry points:</span></span>  
  
-   <span data-ttu-id="52267-178">Conjuntos de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="52267-178">Report datasets.</span></span> <span data-ttu-id="52267-179">Los campos de los conjuntos de datos de informe que se devuelven de las consultas pueden contener cualquier tipo RDL válido.</span><span class="sxs-lookup"><span data-stu-id="52267-179">Fields in report datasets that are returned from queries might contain any valid RDL type.</span></span>  
  
-   <span data-ttu-id="52267-180">Parámetros de informe.</span><span class="sxs-lookup"><span data-stu-id="52267-180">Report parameters.</span></span> <span data-ttu-id="52267-181">Los valores de parámetro proporcionados por el usuario pueden contener cualquier tipo RDL válido.</span><span class="sxs-lookup"><span data-stu-id="52267-181">User-supplied parameter values might contain any valid RDL type.</span></span>  
  
-   <span data-ttu-id="52267-182">Miembros de un tipo habilitado que no están en la lista de bloqueados.</span><span class="sxs-lookup"><span data-stu-id="52267-182">Members of an enabled type that are not in the block list.</span></span> <span data-ttu-id="52267-183">De forma predeterminada, todos los miembros de todos los tipos de la lista de permitidos están habilitados.</span><span class="sxs-lookup"><span data-stu-id="52267-183">By default, all members of all types in the allow list are enabled.</span></span> <span data-ttu-id="52267-184">Al agregar un nombre de miembro a la lista de bloqueados, se están denegando todos los miembros con ese nombre en todos los tipos que están en la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="52267-184">When you add a member name to the block list, you are denying all members with that name across all types that are in the allow list.</span></span>  
  
 <span data-ttu-id="52267-185">Para habilitar un miembro de un tipo pero denegar un miembro con el mismo nombre de otro tipo, debe realizar las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="52267-185">To enable a member of one type but deny a member with the same name for a different type, you must do the following:</span></span>  
  
-   <span data-ttu-id="52267-186">Agregue un **\<Deny>** elemento para el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="52267-186">Add a **\<Deny>** element for the member name.</span></span>  
  
-   <span data-ttu-id="52267-187">Crear un miembro de proxy con otro nombre en una clase de un ensamblado personalizado para el miembro que desea habilitar.</span><span class="sxs-lookup"><span data-stu-id="52267-187">Create a proxy member with a different name on a class in a custom assembly for the member that you want to enable.</span></span>  
  
-   <span data-ttu-id="52267-188">Agregar la nueva clase a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="52267-188">Add that new class to the allow list.</span></span>  
  
 <span data-ttu-id="52267-189">Para agregar funciones de [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework a la lista de permitidos, agregue los tipos correspondientes del espacio de nombres Microsoft.VisualBasic a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="52267-189">To add [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework functions to the allow list, add the corresponding types from the Microsoft.VisualBasic namespace to the allow list.</span></span>  
  
 <span data-ttu-id="52267-190">Para agregar palabras clave de tipo de [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework a la lista de permitidos, agregue el tipo CLR correspondiente a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="52267-190">To add [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework type keywords to the allow list, add the corresponding CLR type to the allow list.</span></span> <span data-ttu-id="52267-191">Por ejemplo, para usar la [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] palabra clave .NET Framework `Integer` , agregue el siguiente fragmento XML al **\<RDLSandboxing>** elemento:</span><span class="sxs-lookup"><span data-stu-id="52267-191">For example, to use the [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework keyword `Integer`, add the following XML fragment to the **\<RDLSandboxing>** element:</span></span>  
  
```  
<Allow Namespace="System">Int32</Allow>  
```  
  
 <span data-ttu-id="52267-192">Para agregar un tipo genérico o que admite valores NULL de [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework a la lista de permitidos, debe realizar las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="52267-192">To add a generic or a [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework nullable type to the allow list, you must do the following:</span></span>  
  
-   <span data-ttu-id="52267-193">Crear un tipo de proxy para el tipo genérico o que admite valores NULL de [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="52267-193">Create a proxy type for the generic or [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework nullable type.</span></span>  
  
-   <span data-ttu-id="52267-194">Agregar el tipo de proxy a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="52267-194">Add the proxy type to the allow list.</span></span>  
  
 <span data-ttu-id="52267-195">Al agregar un tipo de un ensamblado personalizado a la lista de permitidos no se concede permiso de ejecución de forma explícita en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="52267-195">Adding a type from a custom assembly to the allow list does not implicitly grant execute permission on the assembly.</span></span> <span data-ttu-id="52267-196">Debe modificar de forma específica el archivo de seguridad de acceso del código y proporcionar el permiso de ejecución en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="52267-196">You must specifically modify the code access security file and provide execute permission to your assembly.</span></span> <span data-ttu-id="52267-197">Para más información, consulte [Code Access Security in Reporting Services](extensions/secure-development/code-access-security-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="52267-197">For more information, see [Code Access Security in Reporting Services](extensions/secure-development/code-access-security-in-reporting-services.md).</span></span>  
  
#### <a name="maintaining-the-deny-list-of-members"></a><span data-ttu-id="52267-198">Mantenimiento \<Deny> de la lista de miembros</span><span class="sxs-lookup"><span data-stu-id="52267-198">Maintaining the \<Deny> List of Members</span></span>  
 <span data-ttu-id="52267-199">Al agregar un nuevo tipo a la lista de permitidos, use la siguiente lista para determinar cuándo tendrá que actualizar la lista de miembros bloqueados:</span><span class="sxs-lookup"><span data-stu-id="52267-199">When you add a new type to the allow list, use the following list to determine when you might have to update the block list of members:</span></span>  
  
-   <span data-ttu-id="52267-200">Al actualizar un ensamblado personalizado con una versión que introduce nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="52267-200">When you update a custom assembly with a version that introduces new types.</span></span>  
  
-   <span data-ttu-id="52267-201">Al agregar los miembros a los tipos de la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="52267-201">When you add members to the types in the allow list.</span></span>  
  
-   <span data-ttu-id="52267-202">Al actualizar [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="52267-202">When you update the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] on the report server.</span></span>  
  
-   <span data-ttu-id="52267-203">Al actualizar el servidor de informes a una versión posterior de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52267-203">When you upgrade the report server to a later version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="52267-204">Al actualizar un servidor de informes para administrar un esquema RDL posterior, porque se pueden haber agregado nuevos miembros a los tipos RDL.</span><span class="sxs-lookup"><span data-stu-id="52267-204">When you update a report server to handle a later RDL schema, because new members might have been added to RDL types.</span></span>  
  
### <a name="working-with-operators-and-new"></a><span data-ttu-id="52267-205">Trabajar con operadores y New</span><span class="sxs-lookup"><span data-stu-id="52267-205">Working with Operators and New</span></span>  
 <span data-ttu-id="52267-206">De forma predeterminada, los operadores del lenguaje [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework siempre están permitidos, excepto para `New`.</span><span class="sxs-lookup"><span data-stu-id="52267-206">By default, [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework language operators, except for `New`, are always allowed.</span></span> <span data-ttu-id="52267-207">El `New` operador se controla mediante el `AllowNew` atributo del **\<Allow>** elemento.</span><span class="sxs-lookup"><span data-stu-id="52267-207">The `New` operator is controlled by the `AllowNew` attribute on the **\<Allow>** element.</span></span> <span data-ttu-id="52267-208">Siempre se permiten otros operadores de lenguaje, como el operador de descriptor de acceso de colección predeterminado `!` y las [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] macros de conversión de .NET Framework `CInt` .</span><span class="sxs-lookup"><span data-stu-id="52267-208">Other language operators, such as the default collection accessor operator `!` and [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework cast macros such as `CInt`, are always allowed.</span></span>  
  
 <span data-ttu-id="52267-209">No se admite la adición de operadores a la lista de bloqueados, incluidos los operadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="52267-209">Adding operators to a block list, including custom operators, is not supported.</span></span> <span data-ttu-id="52267-210">Para excluir los operadores de un tipo, debe realizar las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="52267-210">To exclude operators for a type, you must do the following:</span></span>  
  
-   <span data-ttu-id="52267-211">Crear un tipo de proxy que no implemente los operadores que desee excluir.</span><span class="sxs-lookup"><span data-stu-id="52267-211">Create a proxy type that does not implement the operators that you want to exclude.</span></span>  
  
-   <span data-ttu-id="52267-212">Agregar el tipo de proxy a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="52267-212">Add the proxy type to the allow list.</span></span>  
  
 <span data-ttu-id="52267-213">Para crear una nueva matriz en una expresión RDL, cree la matriz en un método de una clase que haya definido y agregue dicha clase a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="52267-213">To create a new array in an RDL expression, create the array in a method on a class that you define, and add that class to the allow list.</span></span>  
  
 <span data-ttu-id="52267-214">Para crear una nueva matriz en una expresión RDL, debe realizar las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="52267-214">To create a new array in an RDL expression, you must do the following:</span></span>  
  
-   <span data-ttu-id="52267-215">Definir una nueva clase y crear la matriz en un método de dicha clase.</span><span class="sxs-lookup"><span data-stu-id="52267-215">Define a new class and create the array in a method on that class.</span></span>  
  
-   <span data-ttu-id="52267-216">Agregar la clase a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="52267-216">Add the class to the allow list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52267-217">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52267-217">See Also</span></span>  
 <span data-ttu-id="52267-218">[Archivo de configuración RSReportServer](report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="52267-218">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) </span></span>  
 [<span data-ttu-id="52267-219">Registro de seguimiento del servicio del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="52267-219">Report Server Service Trace Log</span></span>](report-server/report-server-service-trace-log.md)  
  
  
