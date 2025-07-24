# Signal
Signal is a module I made for my games cause I did not wanna use the Roblox bindable events. Good reason, I know.

Dead simple to use, make one with
```lua
local Signal = signal.new()
```
Then fire it via
```lua
Signal:Fire(x,y,z,...)
```
Boom, that's all you need

Then for listening there's
```lua
local Connection = Signal:Connect(function(x,y,z,...)
  -- triggers every time, has to be disconnected via Connection:Disconnect()
end)
local ConnectionOnce = Signal:Once(function(x,y,z,...)
  -- triggers ONCE and auto disconnects, but you can disconnect it manually. I would advise against making the ConnectionOnce variable cause of memory stuff, but your call
end)

Signal:Wait() --... waits... for the signal, duh
```

## Bonus tip:
You can do
```lua
local Signal = signal.new(true,.5)

-- On Fire(), this will cause the event to stall for 0.5 seconds MAXIMUM to execute all the functions connected to it
-- good if you gotta figure out race conditions or smth

```
