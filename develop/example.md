# Example

> The following code is demonstrated in accordance with the TabooLib plugin method
```kotlin
package com.github.username

import taboolib.common.platform.event.SubscribeEvent

/**
 * @project Example
 *
 * @author Score2
 * @since 2021/10/23 22:35
 */
object Demo {
    
    @SubscribeEvent
    fun e(e: MenuOpenEvent) {
        println("玩家: ${e.session.viewer.name} 打开了菜单: ${e.menu.id}")
    }
    
}
```