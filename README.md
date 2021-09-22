# ddp

MeteorJS DDP library for Golang


websocket a io.reader and io.writer 


writeSocketStat (state, WriterProxy) 
                           -->  writeLog (Log, WriterProxy)
			                       --> WebSocket

---------------
WriterStats is a stateTracker + WriterProxy(writeSocketState)
writeSocketStat is a StateTracker + WriterProxy(writeLog), track current socket
writerLog is a Log + WriterProxy(io.Writer)
WriterProxy is a io.Writer of websocket

stateTracker is a mutex + some ints, and implement snapshot to state, 

encoder ==>
   json.Encoder of writeStat

when Encoder encode object, it write to WebSocket


WriterStats and WriterLog both implement io.writer interfce