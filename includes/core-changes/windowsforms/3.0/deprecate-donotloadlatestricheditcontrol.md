---
ms.openlocfilehash: 3f0e8fb4d0d727b40cff5de7cfdc7529bf32dac4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937088"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>不支持 DoNotLoadLatestRichEditControl 兼容性开关

已在 .NET Framework 4.7.1 中引入 `Switch.System.Windows.Forms.UseLegacyImages` 兼容性开关，但它在 .NET Core 3.0 上的 Windows 窗体中尚不受支持。

#### <a name="change-description"></a>更改描述

在 .NET Framework 4.6.2 及更低版本中，<xref:System.Windows.Forms.RichTextBox> 控件会实例化 Win32 RichEdit 控件 v3.0；而对于面向 .NET Framework 4.7.1 的应用程序，<xref:System.Windows.Forms.RichTextBox> 控件会实例化 RichEdit v4.1（位于 msftedit.dll 中）  。 已引入 `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` 兼容性开关，使面向 .NET Framework 4.7.1 及更高版本的应用程序可选择不使用新的 RichEdit v4.1 控件而改用旧的 RichEdit v3 控件。

.NET Core 中尚不支持 `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` 开关。 仅支持 <xref:System.Windows.Forms.RichTextBox> 控件的新版本。

#### <a name="version-introduced"></a>引入的版本

3.0 预览版 9

#### <a name="recommended-action"></a>建议操作

删除此开关。 此开关不受支持，且未提供替代功能。

#### <a name="category"></a>类别

Windows 窗体

#### <a name="affected-apis"></a>受影响的 API

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
