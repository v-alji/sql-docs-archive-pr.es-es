---
title: Capturar datos de eventos de desencadenador logon | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e05b1ab4-c10b-402a-9591-f6ec1e3db8c0
author: rothja
ms.author: jroth
ms.openlocfilehash: b11323702d7468d07783b4d1c763dba691479d9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676945"
---
# <a name="capture-logon-trigger-event-data"></a><span data-ttu-id="6e120-102">Capturar datos de eventos de desencadenador logon</span><span class="sxs-lookup"><span data-stu-id="6e120-102">Capture Logon Trigger Event Data</span></span>
  <span data-ttu-id="6e120-103">Para capturar datos XML acerca de los eventos LOGON para utilizarlos dentro de los desencadenadores logon, utilice la función [EVENTDATA](/sql/t-sql/functions/eventdata-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="6e120-103">To capture XML data about LOGON events for use inside logon triggers, use the [EVENTDATA](/sql/t-sql/functions/eventdata-transact-sql) function.</span></span> <span data-ttu-id="6e120-104">El evento LOGON devuelve el siguiente esquema de datos de eventos:</span><span class="sxs-lookup"><span data-stu-id="6e120-104">The LOGON event returns the following event data schema:</span></span>  
  
 `<EVENT_INSTANCE>`  
  
 `<EventType>event_type</EventType>`  
  
 `<PostTime>post_time</PostTime>`  
  
 `<SPID>spid</SPID>`  
  
 `<ServerName>server_name</ServerName>`  
  
 `<LoginName>login_name</LoginName>`  
  
 `<LoginType>login_type</LoginType>`  
  
 `<SID>sid</SID>`  
  
 `<ClientHost>client_host</ClientHost>`  
  
 `<IsPooled>is_pooled</IsPooled>`  
  
 `</EVENT_INSTANCE>`  
  
 `<EventType>`  
 <span data-ttu-id="6e120-105">Contiene `LOGON`.</span><span class="sxs-lookup"><span data-stu-id="6e120-105">Contains `LOGON`.</span></span>  
  
 `<PostTime>`  
 <span data-ttu-id="6e120-106">Contiene la hora en la que se solicita que se establezca una sesión.</span><span class="sxs-lookup"><span data-stu-id="6e120-106">Contains the time when a session is requested to be established.</span></span>  
  
 `<SID>`  
 <span data-ttu-id="6e120-107">Contiene el flujo binario codificado de base 64 del número de identificación de seguridad (SID) para el nombre de inicio de sesión especificado.</span><span class="sxs-lookup"><span data-stu-id="6e120-107">Contains the base 64-encoded binary stream of the security identification number (SID) for the specified login name.</span></span>  
  
 `<ClientHost>`  
 <span data-ttu-id="6e120-108">Contiene el nombre de host del cliente desde el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="6e120-108">Contains the host name of the client from where the connection is made.</span></span> <span data-ttu-id="6e120-109">El valor es '`<local_machine>`' si el nombre del cliente y del servidor son iguales.</span><span class="sxs-lookup"><span data-stu-id="6e120-109">The value is '`<local_machine>`' if the client and server name are the same.</span></span> <span data-ttu-id="6e120-110">De lo contrario, el valor es la dirección IP del cliente.</span><span class="sxs-lookup"><span data-stu-id="6e120-110">Otherwise, the value is the IP address of the client.</span></span>  
  
 `<IsPooled>`  
 <span data-ttu-id="6e120-111">Es `1` si la conexión se vuelve a utilizar empleando la agrupación de conexiones.</span><span class="sxs-lookup"><span data-stu-id="6e120-111">Is `1` if the connection is reused by using connection pooling.</span></span> <span data-ttu-id="6e120-112">De lo contrario, el valor es `0`.</span><span class="sxs-lookup"><span data-stu-id="6e120-112">Otherwise, the value is `0`.</span></span>  
  
  
