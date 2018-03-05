 ### Cocos 的一些笔记
 - Version Cocos2d-x 3.10
 - Language Lua 5.1 JIT
 - UI CocosStudio
 - Editor VSCode with luaide tools -v0.3.7
 
 
 
 #### 1、触摸监听
 normal: 这种监听不知道到底点击了控件的哪个位置
  ``` lua
  local btn = ccui.ImageView("test/HelloWorld.png")
  self:addChild(btn)
  btn:addTouchEventListener(function(sender, touchType)
    -- write your code
  end)
  ```
  
  hard:
  ``` lua
    self._listener = cc.EventListenerTouchOneByOne:create()
    self._listener:registerScriptHandler(handler(self, self._onTouchBegan), cc.Handler.EVENT_TOUCH_BEGAN)
    self._listener:registerScriptHandler(handler(self, self._onTouchEnded), cc.Handler.EVENT_TOUCH_ENDED)
    self._listener:registerScriptHandler(handler(self, self._onTouchMoved), cc.Handler.EVENT_TOUCH_MOVED)
    self._container = ccui.Layout:create("test/HelloWorld.png")
    local dispatcher = self._container:getEventDispatcher()
    dispatcher:addEventListenerWithSceneGraphPriority(self._listener, self._container)
    
    local function _onTouchBegan(touch, event)
    
    end
    
    local function _onTouchEnded(touch, event)
    
    end
    
    local function _onTouchMoved(touch, event)
   
    end
    
    --[[这里可以通过 touch:getLocation() 来获得触摸坐标， 也可以通过Node的ConvertSpaceNode 来转换到对应的局部坐标
      需要注意的是，这个触摸是针对层的，也就是说当前屏幕都会响应触摸的begin，自己调整，来决定是否触发moved和ended
      若 began 中返回false， 则不处理moved和ended了]]
  ```
 
