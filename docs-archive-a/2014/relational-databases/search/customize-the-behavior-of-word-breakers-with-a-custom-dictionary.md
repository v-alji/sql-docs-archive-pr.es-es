---
title: Personalización del comportamiento de separadores de palabras con un diccionario personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: a8e278d1-aeaa-48f1-a0c6-5de232c983e4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9fb02a47da20134925d9b2486ea0c08091af4aa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746224"
---
# <a name="customize-the-behavior-of-word-breakers-with-a-custom-dictionary"></a><span data-ttu-id="b4d28-102">Personalizar el comportamiento de separadores de palabras con un diccionario personalizado</span><span class="sxs-lookup"><span data-stu-id="b4d28-102">Customize the Behavior of Word Breakers with a Custom Dictionary</span></span>
  <span data-ttu-id="b4d28-103">Puede personalizar el comportamiento del separador de palabras para un idioma determinado creando un archivo de diccionario personalizado específico del idioma.</span><span class="sxs-lookup"><span data-stu-id="b4d28-103">You can customize the behavior of the word breaker for a particular language by creating a language-specific custom dictionary file.</span></span> <span data-ttu-id="b4d28-104">Por ejemplo, puede evitar que el separador de palabras separe algunos términos o patrones.</span><span class="sxs-lookup"><span data-stu-id="b4d28-104">For example, you can prevent the word breaker from breaking certain terms or patterns.</span></span>  
  
 <span data-ttu-id="b4d28-105">Para obtener más información, vea el artículo siguiente de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="b4d28-105">For more information, see the following SharePoint article:</span></span>  
  
 [<span data-ttu-id="b4d28-106">Cree un diccionario personalizado (SharePoint Server 2010)</span><span class="sxs-lookup"><span data-stu-id="b4d28-106">Create a custom dictionary (SharePoint Server 2010)</span></span>](https://go.microsoft.com/fwlink/?LinkId=215011)  
  
 <span data-ttu-id="b4d28-107">Para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], coloque los archivos de diccionario personalizado en la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="b4d28-107">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], place custom dictionary files in the following folder:</span></span>  
  
 `C:\Program Files\Microsoft SQL Server\<instance name>\MSSQL\Binn`  
  
 <span data-ttu-id="b4d28-108">Después de crear o cambiar los archivos de diccionario personalizado, reinicie el Selector de demonio de filtro de texto completo de SQL con el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4d28-108">After creating or changing custom dictionary files, restart the SQL Full-text Daemon Launcher with the following command:</span></span>  
  
 `exec sp_fulltext_service 'restart_all_fdhosts'`  
  
  
