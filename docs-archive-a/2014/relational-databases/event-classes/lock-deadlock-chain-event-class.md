---
title: Clase de eventos Lock:Deadlock Chain | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Deadlock Chain event class
ms.assetid: 9883127b-aa34-4235-88cc-c161cd2112cc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8fb019e0f7922851a76d6a43439c2d3e7dcc6b6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674820"
---
# <a name="lockdeadlock-chain-event-class"></a><span data-ttu-id="5278c-102">Lock:Deadlock Chain (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5278c-102">Lock:Deadlock Chain Event Class</span></span>
  <span data-ttu-id="5278c-103">La clase de eventos Lock:Deadlock Chain se produce para cada participante en un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="5278c-103">The Lock:Deadlock Chain event class is produced for each participant in a deadlock.</span></span>  
  
 <span data-ttu-id="5278c-104">Utilice la clase de eventos Lock:Deadlock Chain para supervisar si se cumplen las condiciones del interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="5278c-104">Use the Lock:Deadlock Chain event class to monitor when deadlock conditions occur.</span></span> <span data-ttu-id="5278c-105">Esta información es útil para determinar si los interbloqueos afectan de forma significativa al rendimiento de la aplicación y qué objetos están implicados.</span><span class="sxs-lookup"><span data-stu-id="5278c-105">This information is useful to determine if deadlocks are significantly affecting the performance of your application, and which objects are involved.</span></span> <span data-ttu-id="5278c-106">Se puede examinar el código de la aplicación que modifica estos objetos para determinar si se pueden realizar cambios para minimizar los interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="5278c-106">You can examine the application code that modifies these objects to determine if changes to minimize deadlocks can be made.</span></span>  
  
## <a name="lockdeadlock-chain-event-class-data-columns"></a><span data-ttu-id="5278c-107">Columnas de datos de la clase de eventos Lock:Deadlock Chain</span><span class="sxs-lookup"><span data-stu-id="5278c-107">Lock:Deadlock Chain Event Class Data Columns</span></span>  
  
|<span data-ttu-id="5278c-108">Nombre de columna de datos</span><span class="sxs-lookup"><span data-stu-id="5278c-108">Data column name</span></span>|<span data-ttu-id="5278c-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="5278c-109">Data type</span></span>|<span data-ttu-id="5278c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5278c-110">Description</span></span>|<span data-ttu-id="5278c-111">Identificador de columna</span><span class="sxs-lookup"><span data-stu-id="5278c-111">Column ID</span></span>|<span data-ttu-id="5278c-112">Filtrable</span><span class="sxs-lookup"><span data-stu-id="5278c-112">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="5278c-113">BinaryData</span><span class="sxs-lookup"><span data-stu-id="5278c-113">BinaryData</span></span>|`image`|<span data-ttu-id="5278c-114">Identificador del recurso de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5278c-114">Lock resource identifier.</span></span>|<span data-ttu-id="5278c-115">2</span><span class="sxs-lookup"><span data-stu-id="5278c-115">2</span></span>|<span data-ttu-id="5278c-116">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-116">Yes</span></span>|  
|<span data-ttu-id="5278c-117">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="5278c-117">DatabaseID</span></span>|`int`|<span data-ttu-id="5278c-118">Identificador de la base de datos a la que pertenece este recurso.</span><span class="sxs-lookup"><span data-stu-id="5278c-118">ID of the database to which this resource belongs.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="5278c-119">muestra el nombre de la base de datos si se captura la columna de datos ServerName en el seguimiento y el servidor está disponible.</span><span class="sxs-lookup"><span data-stu-id="5278c-119">displays the name of the database if the ServerName data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="5278c-120">Determina el valor de una base de datos mediante la función DB_ID.</span><span class="sxs-lookup"><span data-stu-id="5278c-120">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="5278c-121">3</span><span class="sxs-lookup"><span data-stu-id="5278c-121">3</span></span>|<span data-ttu-id="5278c-122">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-122">Yes</span></span>|  
|<span data-ttu-id="5278c-123">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="5278c-123">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="5278c-124">Nombre de la base de datos a la que pertenece el recurso.</span><span class="sxs-lookup"><span data-stu-id="5278c-124">Name of the database to which the resource belongs.</span></span>|<span data-ttu-id="5278c-125">35</span><span class="sxs-lookup"><span data-stu-id="5278c-125">35</span></span>|<span data-ttu-id="5278c-126">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-126">Yes</span></span>|  
|<span data-ttu-id="5278c-127">EventClass</span><span class="sxs-lookup"><span data-stu-id="5278c-127">EventClass</span></span>|`int`|<span data-ttu-id="5278c-128">Tipo de evento = 59.</span><span class="sxs-lookup"><span data-stu-id="5278c-128">Type of event = 59.</span></span>|<span data-ttu-id="5278c-129">27</span><span class="sxs-lookup"><span data-stu-id="5278c-129">27</span></span>|<span data-ttu-id="5278c-130">No</span><span class="sxs-lookup"><span data-stu-id="5278c-130">No</span></span>|  
|<span data-ttu-id="5278c-131">EventSequence</span><span class="sxs-lookup"><span data-stu-id="5278c-131">EventSequence</span></span>|`int`|<span data-ttu-id="5278c-132">Secuencia de un evento determinado de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="5278c-132">Sequence of a given event within the request.</span></span>|<span data-ttu-id="5278c-133">51</span><span class="sxs-lookup"><span data-stu-id="5278c-133">51</span></span>|<span data-ttu-id="5278c-134">No</span><span class="sxs-lookup"><span data-stu-id="5278c-134">No</span></span>|  
|<span data-ttu-id="5278c-135">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="5278c-135">EventSubClass</span></span>|`int`|<span data-ttu-id="5278c-136">Tipo de la subclase de eventos.</span><span class="sxs-lookup"><span data-stu-id="5278c-136">Type of event subclass.</span></span><br /><br /> <span data-ttu-id="5278c-137">101=Tipo de recurso Bloqueo</span><span class="sxs-lookup"><span data-stu-id="5278c-137">101=Resource type Lock</span></span><br /><br /> <span data-ttu-id="5278c-138">102=Tipo de recurso Intercambio</span><span class="sxs-lookup"><span data-stu-id="5278c-138">102=Resource type Exchange</span></span>|<span data-ttu-id="5278c-139">21</span><span class="sxs-lookup"><span data-stu-id="5278c-139">21</span></span>|<span data-ttu-id="5278c-140">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-140">Yes</span></span>|  
|<span data-ttu-id="5278c-141">IntegerData</span><span class="sxs-lookup"><span data-stu-id="5278c-141">IntegerData</span></span>|`int`|<span data-ttu-id="5278c-142">Número de interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="5278c-142">Deadlock number.</span></span> <span data-ttu-id="5278c-143">Los números se asignan a partir de 0 cuando se inicia el servidor y se incrementan para cada interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="5278c-143">Numbers are assigned beginning with 0 when the server is started, and incremented for each deadlock.</span></span>|<span data-ttu-id="5278c-144">25</span><span class="sxs-lookup"><span data-stu-id="5278c-144">25</span></span>|<span data-ttu-id="5278c-145">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-145">Yes</span></span>|  
|<span data-ttu-id="5278c-146">IntegerData2</span><span class="sxs-lookup"><span data-stu-id="5278c-146">IntegerData2</span></span>|`int`|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|<span data-ttu-id="5278c-147">55</span><span class="sxs-lookup"><span data-stu-id="5278c-147">55</span></span>|<span data-ttu-id="5278c-148">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-148">Yes</span></span>|  
|<span data-ttu-id="5278c-149">IsSystem</span><span class="sxs-lookup"><span data-stu-id="5278c-149">IsSystem</span></span>|`int`|<span data-ttu-id="5278c-150">Indica si el evento ha ocurrido en un proceso del sistema o en un proceso de usuario.</span><span class="sxs-lookup"><span data-stu-id="5278c-150">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="5278c-151">1 = sistema, 0 = usuario.</span><span class="sxs-lookup"><span data-stu-id="5278c-151">1 = system, 0 = user.</span></span>|<span data-ttu-id="5278c-152">60</span><span class="sxs-lookup"><span data-stu-id="5278c-152">60</span></span>|<span data-ttu-id="5278c-153">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-153">Yes</span></span>|  
|<span data-ttu-id="5278c-154">LoginSid</span><span class="sxs-lookup"><span data-stu-id="5278c-154">LoginSid</span></span>|`image`|<span data-ttu-id="5278c-155">SID (número de identificación de seguridad) del usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="5278c-155">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="5278c-156">Puede buscar esta información en la vista de catálogo sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="5278c-156">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="5278c-157">Cada SID es único para cada inicio de sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="5278c-157">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="5278c-158">41</span><span class="sxs-lookup"><span data-stu-id="5278c-158">41</span></span>|<span data-ttu-id="5278c-159">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-159">Yes</span></span>|  
|<span data-ttu-id="5278c-160">Mode</span><span class="sxs-lookup"><span data-stu-id="5278c-160">Mode</span></span>|`int`|<span data-ttu-id="5278c-161">0=NULL: Compatible con los demás modos de bloqueo (LCK_M_NL)</span><span class="sxs-lookup"><span data-stu-id="5278c-161">0=NULL - Compatible with all other lock modes (LCK_M_NL)</span></span><br /><br /> <span data-ttu-id="5278c-162">1=Bloqueo Estabilidad del esquema (LCK_M_SCH_S)</span><span class="sxs-lookup"><span data-stu-id="5278c-162">1=Schema Stability lock (LCK_M_SCH_S)</span></span><br /><br /> <span data-ttu-id="5278c-163">2=Bloqueo Modificación del esquema (LCK_M_SCH_M)</span><span class="sxs-lookup"><span data-stu-id="5278c-163">2=Schema Modification Lock (LCK_M_SCH_M)</span></span><br /><br /> <span data-ttu-id="5278c-164">3=Bloqueo Compartido (LCK_M_S)</span><span class="sxs-lookup"><span data-stu-id="5278c-164">3=Shared Lock (LCK_M_S)</span></span><br /><br /> <span data-ttu-id="5278c-165">4=Bloqueo Actualizar (LCK_M_U)</span><span class="sxs-lookup"><span data-stu-id="5278c-165">4=Update Lock (LCK_M_U)</span></span><br /><br /> <span data-ttu-id="5278c-166">5=Bloqueo Exclusivo (LCK_M_X)</span><span class="sxs-lookup"><span data-stu-id="5278c-166">5=Exclusive Lock (LCK_M_X)</span></span><br /><br /> <span data-ttu-id="5278c-167">6=Bloqueo Intención compartida (LCK_M_IS)</span><span class="sxs-lookup"><span data-stu-id="5278c-167">6=Intent Shared Lock (LCK_M_IS)</span></span><br /><br /> <span data-ttu-id="5278c-168">7=Bloqueo Actualizar intención (LCK_M_IU)</span><span class="sxs-lookup"><span data-stu-id="5278c-168">7=Intent Update Lock (LCK_M_IU)</span></span><br /><br /> <span data-ttu-id="5278c-169">8=Bloqueo Intención exclusiva (LCK_M_IX)</span><span class="sxs-lookup"><span data-stu-id="5278c-169">8=Intent Exclusive Lock (LCK_M_IX)</span></span><br /><br /> <span data-ttu-id="5278c-170">9=Actualizar intención compartida (LCK_M_SIU)</span><span class="sxs-lookup"><span data-stu-id="5278c-170">9=Shared with intent to Update (LCK_M_SIU)</span></span><br /><br /> <span data-ttu-id="5278c-171">10=Intención compartida exclusiva (LCK_M_SIX)</span><span class="sxs-lookup"><span data-stu-id="5278c-171">10=Shared with Intent Exclusive (LCK_M_SIX)</span></span><br /><br /> <span data-ttu-id="5278c-172">11=Actualizar intención exclusiva (LCK_M_UIX)</span><span class="sxs-lookup"><span data-stu-id="5278c-172">11=Update with Intent Exclusive (LCK_M_UIX)</span></span><br /><br /> <span data-ttu-id="5278c-173">12=Bloqueo Actualización masiva (LCK_M_BU)</span><span class="sxs-lookup"><span data-stu-id="5278c-173">12=Bulk Update Lock (LCK_M_BU)</span></span><br /><br /> <span data-ttu-id="5278c-174">13=Intervalo de claves compartido/compartido (LCK_M_RS_S)</span><span class="sxs-lookup"><span data-stu-id="5278c-174">13=Key range Shared/Shared (LCK_M_RS_S)</span></span><br /><br /> <span data-ttu-id="5278c-175">14=Intervalo de claves compartido/actualización (LCK_M_RS_U)</span><span class="sxs-lookup"><span data-stu-id="5278c-175">14=Key range Shared/Update (LCK_M_RS_U)</span></span><br /><br /> <span data-ttu-id="5278c-176">15=Intervalo de claves de inserción NULL (LCK_M_RI_NL)</span><span class="sxs-lookup"><span data-stu-id="5278c-176">15=Key Range Insert NULL (LCK_M_RI_NL)</span></span><br /><br /> <span data-ttu-id="5278c-177">16=Intervalo de claves de inserción compartido (LCK_M_RI_S)</span><span class="sxs-lookup"><span data-stu-id="5278c-177">16=Key Range Insert Shared (LCK_M_RI_S)</span></span><br /><br /> <span data-ttu-id="5278c-178">17=Intervalo de claves de inserción de actualización (LCK_M_RI_U)</span><span class="sxs-lookup"><span data-stu-id="5278c-178">17=Key Range Insert Update (LCK_M_RI_U)</span></span><br /><br /> <span data-ttu-id="5278c-179">18=Intervalo de claves de inserción exclusivo (LCK_M_RI_X)</span><span class="sxs-lookup"><span data-stu-id="5278c-179">18=Key Range Insert Exclusive (LCK_M_RI_X)</span></span><br /><br /> <span data-ttu-id="5278c-180">19=Intervalo de claves exclusivo compartido (LCK_M_RX_S)</span><span class="sxs-lookup"><span data-stu-id="5278c-180">19=Key Range Exclusive Shared (LCK_M_RX_S)</span></span><br /><br /> <span data-ttu-id="5278c-181">20=Intervalo de claves exclusivo de actualización (LCK_M_RX_U)</span><span class="sxs-lookup"><span data-stu-id="5278c-181">20=Key Range Exclusive Update (LCK_M_RX_U)</span></span><br /><br /> <span data-ttu-id="5278c-182">21=Intervalo de claves exclusivo exclusivo (LCK_M_RX_X)</span><span class="sxs-lookup"><span data-stu-id="5278c-182">21=Key Range Exclusive Exclusive (LCK_M_RX_X)</span></span>|<span data-ttu-id="5278c-183">32</span><span class="sxs-lookup"><span data-stu-id="5278c-183">32</span></span>|<span data-ttu-id="5278c-184">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-184">Yes</span></span>|  
|<span data-ttu-id="5278c-185">ObjectID</span><span class="sxs-lookup"><span data-stu-id="5278c-185">ObjectID</span></span>|`int`|<span data-ttu-id="5278c-186">Id. del objeto bloqueado, si está disponible y es aplicable.</span><span class="sxs-lookup"><span data-stu-id="5278c-186">ID of the object that was locked, if available and applicable.</span></span>|<span data-ttu-id="5278c-187">22</span><span class="sxs-lookup"><span data-stu-id="5278c-187">22</span></span>|<span data-ttu-id="5278c-188">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-188">Yes</span></span>|  
|<span data-ttu-id="5278c-189">ObjectID2</span><span class="sxs-lookup"><span data-stu-id="5278c-189">ObjectID2</span></span>|`bigint`|<span data-ttu-id="5278c-190">Id. del objeto o entidad relacionado, si está disponible y es aplicable.</span><span class="sxs-lookup"><span data-stu-id="5278c-190">The ID of the related object or entity, if available and applicable.</span></span>|<span data-ttu-id="5278c-191">56</span><span class="sxs-lookup"><span data-stu-id="5278c-191">56</span></span>|<span data-ttu-id="5278c-192">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-192">Yes</span></span>|  
|<span data-ttu-id="5278c-193">OwnerID</span><span class="sxs-lookup"><span data-stu-id="5278c-193">OwnerID</span></span>|`int`|<span data-ttu-id="5278c-194">1=TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="5278c-194">1=TRANSACTION</span></span><br /><br /> <span data-ttu-id="5278c-195">2=CURSOR</span><span class="sxs-lookup"><span data-stu-id="5278c-195">2=CURSOR</span></span><br /><br /> <span data-ttu-id="5278c-196">3=SESSION</span><span class="sxs-lookup"><span data-stu-id="5278c-196">3=SESSION</span></span><br /><br /> <span data-ttu-id="5278c-197">4=SHARED_TRANSACTION_WORKSPACE</span><span class="sxs-lookup"><span data-stu-id="5278c-197">4=SHARED_TRANSACTION_WORKSPACE</span></span><br /><br /> <span data-ttu-id="5278c-198">5=EXCLUSIVE_TRANSACTION_WORKSPACE</span><span class="sxs-lookup"><span data-stu-id="5278c-198">5=EXCLUSIVE_TRANSACTION_WORKSPACE</span></span>|<span data-ttu-id="5278c-199">58</span><span class="sxs-lookup"><span data-stu-id="5278c-199">58</span></span>|<span data-ttu-id="5278c-200">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-200">Yes</span></span>|  
|<span data-ttu-id="5278c-201">RequestID</span><span class="sxs-lookup"><span data-stu-id="5278c-201">RequestID</span></span>|`int`|<span data-ttu-id="5278c-202">Identificador de la solicitud que contiene la instrucción.</span><span class="sxs-lookup"><span data-stu-id="5278c-202">ID of the request containing the statement.</span></span>|<span data-ttu-id="5278c-203">49</span><span class="sxs-lookup"><span data-stu-id="5278c-203">49</span></span>|<span data-ttu-id="5278c-204">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-204">Yes</span></span>|  
|<span data-ttu-id="5278c-205">nombreDeServidor</span><span class="sxs-lookup"><span data-stu-id="5278c-205">ServerName</span></span>|`nvarchar`|<span data-ttu-id="5278c-206">Nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la que se realiza un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5278c-206">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="5278c-207">26</span><span class="sxs-lookup"><span data-stu-id="5278c-207">26</span></span>|<span data-ttu-id="5278c-208">No</span><span class="sxs-lookup"><span data-stu-id="5278c-208">No</span></span>|  
|<span data-ttu-id="5278c-209">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="5278c-209">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="5278c-210">Nombre de inicio de sesión del usuario que originó la sesión.</span><span class="sxs-lookup"><span data-stu-id="5278c-210">Login name of the user who originated the session.</span></span> <span data-ttu-id="5278c-211">Por ejemplo, si se conecta a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando inicioDeSesión1 y ejecuta una instrucción como inicioDeSesión2, SessionLoginName muestra inicioDeSesión1 y LoginName muestra inicioDeSesión2.</span><span class="sxs-lookup"><span data-stu-id="5278c-211">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, SessionLoginName shows Login1 and LoginName shows Login2.</span></span> <span data-ttu-id="5278c-212">En esta columna se muestran los inicios de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="5278c-212">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows logins.</span></span>|<span data-ttu-id="5278c-213">64</span><span class="sxs-lookup"><span data-stu-id="5278c-213">64</span></span>|<span data-ttu-id="5278c-214">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-214">Yes</span></span>|  
|<span data-ttu-id="5278c-215">SPID</span><span class="sxs-lookup"><span data-stu-id="5278c-215">SPID</span></span>|`int`|<span data-ttu-id="5278c-216">Identificador de la sesión en la que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="5278c-216">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="5278c-217">12</span><span class="sxs-lookup"><span data-stu-id="5278c-217">12</span></span>|<span data-ttu-id="5278c-218">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-218">Yes</span></span>|  
|<span data-ttu-id="5278c-219">StartTime</span><span class="sxs-lookup"><span data-stu-id="5278c-219">StartTime</span></span>|`datetime`|<span data-ttu-id="5278c-220">Hora a la que se inició el evento, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="5278c-220">Time at which the event started, if available.</span></span>|<span data-ttu-id="5278c-221">14</span><span class="sxs-lookup"><span data-stu-id="5278c-221">14</span></span>|<span data-ttu-id="5278c-222">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-222">Yes</span></span>|  
|<span data-ttu-id="5278c-223">TextData</span><span class="sxs-lookup"><span data-stu-id="5278c-223">TextData</span></span>|`ntext`|<span data-ttu-id="5278c-224">Valor de texto que depende del tipo de recurso.</span><span class="sxs-lookup"><span data-stu-id="5278c-224">Text value dependent on the resource type.</span></span>|<span data-ttu-id="5278c-225">1</span><span class="sxs-lookup"><span data-stu-id="5278c-225">1</span></span>|<span data-ttu-id="5278c-226">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-226">Yes</span></span>|  
|<span data-ttu-id="5278c-227">TransactionID</span><span class="sxs-lookup"><span data-stu-id="5278c-227">TransactionID</span></span>|`bigint`|<span data-ttu-id="5278c-228">Id. de la transacción asignado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="5278c-228">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="5278c-229">4</span><span class="sxs-lookup"><span data-stu-id="5278c-229">4</span></span>|<span data-ttu-id="5278c-230">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-230">Yes</span></span>|  
|<span data-ttu-id="5278c-231">Tipo</span><span class="sxs-lookup"><span data-stu-id="5278c-231">Type</span></span>|`int`|<span data-ttu-id="5278c-232">1=NULL_RESOURCE</span><span class="sxs-lookup"><span data-stu-id="5278c-232">1=NULL_RESOURCE</span></span><br /><br /> <span data-ttu-id="5278c-233">2=DATABASE</span><span class="sxs-lookup"><span data-stu-id="5278c-233">2=DATABASE</span></span><br /><br /> <span data-ttu-id="5278c-234">3=FILE</span><span class="sxs-lookup"><span data-stu-id="5278c-234">3=FILE</span></span><br /><br /> <span data-ttu-id="5278c-235">5=OBJECT</span><span class="sxs-lookup"><span data-stu-id="5278c-235">5=OBJECT</span></span><br /><br /> <span data-ttu-id="5278c-236">6=PAGE</span><span class="sxs-lookup"><span data-stu-id="5278c-236">6=PAGE</span></span><br /><br /> <span data-ttu-id="5278c-237">7=KEY</span><span class="sxs-lookup"><span data-stu-id="5278c-237">7=KEY</span></span><br /><br /> <span data-ttu-id="5278c-238">8=EXTENT</span><span class="sxs-lookup"><span data-stu-id="5278c-238">8=EXTENT</span></span><br /><br /> <span data-ttu-id="5278c-239">9=RID</span><span class="sxs-lookup"><span data-stu-id="5278c-239">9=RID</span></span><br /><br /> <span data-ttu-id="5278c-240">10=APPLICATION</span><span class="sxs-lookup"><span data-stu-id="5278c-240">10=APPLICATION</span></span><br /><br /> <span data-ttu-id="5278c-241">11=METADATA</span><span class="sxs-lookup"><span data-stu-id="5278c-241">11=METADATA</span></span><br /><br /> <span data-ttu-id="5278c-242">12=AUTONAMEDB</span><span class="sxs-lookup"><span data-stu-id="5278c-242">12=AUTONAMEDB</span></span><br /><br /> <span data-ttu-id="5278c-243">13=HOBT</span><span class="sxs-lookup"><span data-stu-id="5278c-243">13=HOBT</span></span><br /><br /> <span data-ttu-id="5278c-244">14=ALLOCATION_UNIT</span><span class="sxs-lookup"><span data-stu-id="5278c-244">14=ALLOCATION_UNIT</span></span>|<span data-ttu-id="5278c-245">57</span><span class="sxs-lookup"><span data-stu-id="5278c-245">57</span></span>|<span data-ttu-id="5278c-246">Sí</span><span class="sxs-lookup"><span data-stu-id="5278c-246">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5278c-247">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5278c-247">See Also</span></span>  
 <span data-ttu-id="5278c-248">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5278c-248">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="5278c-249">sys.dm_tran_locks &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5278c-249">sys.dm_tran_locks &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql)  
  
  