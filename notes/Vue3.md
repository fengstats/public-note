Vue3 关于 watch 监听异常的问题：[Vue SFC Playground](https://play.vuejs.org/#eNp9Ustu2zAQ/JUtL3IAV0bqmysbfaVAe2iNpuiJF0ZeWUookiAp24Cgf++StGWljxz82J3Z4Sw5PXtvTH7okK1Y4UrbGA8OfWc2XDWt0dZDDxYrGKCyuoWMqNkIfdStOffzRSiCUvaWq1IrF4SELevP2rafhBewDkKzniuAHdVOd7bEFWTZnKvh5jLUuPtaH8/kSkiHI1TKpnwiZHYD603USeT8IGSHBLya1iTKVbFIS9E6VHhsjRQeqer75+4GIgMUD533WsG7eNSas/jL2ebBk1QCaZiIcfWVsdq4rbCidUTu8zz/Q5VGi3gzacrA4XVTETUZJfT2zbJYBLRYjO7YnHlHK1fNPn90WtHbxG3JDik1Eu134xu6Es5WEJGACSn18WvsedshXWrqlzWWT//oP7pT6HG2tejQHpCzEfPC7tEn+O7+G57o/wi2etdJYr8A/kCnZRc8JtqHTu3I9oQX3X6JMWrU/qe7O3lU7rJUMBqYQ+RzRrEKl/i/1a92l/kyztHj0y1eIvl3uO0k3kfhy/p5wAkOnxS7+MiUrh1WjcJtqCjFBNPZkwCQnyF0Kcr0HUVnMamJlE+oc5hRROeg5e6XkJFzEYRwppaYS72fZVElmwOxo2rSvob67HMS7KhS1Lebvp+ag2EoFtRN49ekDb8BKb5eEQ==)

17:35 因为父组件内的 template 中使用了 isShow 用于控制显示/隐藏，每次更新 isShow 的值都会重新渲染一次 template，且你在进行子组件的 props 传值的时候使用的是 `…`（解构赋值），意味着每次传入子组件内的 propsParams 都是不一样的，自然会触发 watch 监听

- 验证：要么把使用 isShow 变量的 `<p>` 去掉
- 解决：改成 `:propsParams="searchFormData"`
