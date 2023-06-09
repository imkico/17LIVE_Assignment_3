# 17LIVE_Assignment_3
- 3-1 請說明 Flux, Redux, Vuex 之間的差異
Flux、Redux和Vuex都是用於管理應用程序狀態，主要的差別如下

Flux是一種架構模式，是由Facebook創建。它提供了一種單向數據流的方式來管理應用程序狀態。Flux架構包含以下四個主要部分：Action, Dispatcher, Store, View。
Action描述了應用程序中發生的事件，Dispatcher將Action分發給Store，Store保存應用程序狀態，View從Store獲取狀態並將其渲染到螢幕上。

Redux是一個基於Flux模式的JavaScript library，為React.js所用，它將應用程序狀態存儲在一個單一的JavaScript對象中，稱為Store。Redux使用純函數來更新狀態。
Redux的三個主要元素是Action, Reducer 和 Store。Action描述了對狀態的更改，Reducer接收Action並返回新的狀態，Store存儲應用程序的狀態。

Vuex是Vue.js的狀態管理庫，它將應用程序的狀態存儲在一個集中的Store中，並且通過使用Mutation和Action來修改狀態。
Vuex 的四個主要元素是: State, Mutation, Action和Getter。State存儲應用程序的狀態，Mutation接收State並直接修改它，Action 接收State並觸發Mutation，Getter則用來計算State的值。

- 3-2 請說明單向資料流與雙向資料流在處理資料更新上的異同

單向資料流指的是資料從父元件流向子元件，由父元件控制資料的更新。在這種模式下，子元件只能通過呼叫父元件的回調函數來改變父元件的狀態，進而更新子元件的資料。這種模式適用於應用程序中資料更新的層次結構比較簡單的情況，例如傳遞數據到子元件渲染列表。

雙向資料流則是指資料可以在元件之間雙向流動。這種模式下，資料可以從父元件流向子元件，同時也可以從子元件流向父元件。這種模式適用於需要經常更新的資料，例如表單輸入框等。在雙向資料流中，子元件可以通過改變自身的狀態來更新父元件的資料，同時父元件也可以通過改變自身的狀態來更新子元件的資料。

- 3-3 這些設計主要想要解決什麼樣的問題? 優缺點為何？

這些設計主要要解決資料流動的方式，讓父元件及子元件可以做資料的交流。

單向資料流的更新只能由父元件進行控制，所以資料會在單方向流動而不會有意外修改的問題。單向資料流的優點有，可維護性較高，可測試性強，因為資料流動的方向明確，可以更容易掌握邏輯，然而，缺點就是在應用程式設計上必須一直保持資料流動的一致性，而如果資料需要更新時候，處理上會較為繁瑣，因為需要透過callback函數將資料更新到父元件。

雙向資料流則允許資料在父元件及子元件之間雙向流動，如此可以更快速地更新資料，像是表單等等需要頻繁更新資料的狀況下，使用雙向資料流可以簡化程式碼並且不需要使用額外的callback函式，然而，雙向資料流的缺點是在多重資料流的架構下，容易產生資料亂流問題，而讓整體程式碼難以追蹤及維護。
