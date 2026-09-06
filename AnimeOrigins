-- KIDz protected distribution loader
-- This loader intentionally does not contain the protected hub source or payload key.
local hszLiosGIhcC=game:GetService("HttpService")
local pskpPiqJBdQa=game:GetService("Players")
local lpRHXBpkBedf=pskpPiqJBdQa.LocalPlayer
local b3ncGiELGppM=bit32
local lsJxoMByWaao=loadstring
if type(lsJxoMByWaao)~="function" then error("KIDz: loadstring unavailable") end
if type(b3ncGiELGppM)~="table" then error("KIDz: bit32 unavailable") end

local aphjYbPKcjFO="https://kidz-license-api"..".xyasubmungm".."iruhrxkkupenkhir.worke".."rs"..".dev"
local biJbCBXAGjyN="bld".."_45b0e".."82259d".."8b503"
local lidTLXpjdRNP="KIDZ".."-".."bMBnKapK".."CpXcydAW3".."tWuiAC690".."p9qZ".."zA"

local function reiuLwhSIJeZ()
    local e=(getgenv and getgenv()) or _G
    local c={
        e and e.request,
        e and e.http_request,
        e and e.httprequest,
        type(e)=="table" and type(e.syn)=="table" and e.syn.request or nil,
        type(e)=="table" and type(e.http)=="table" and e.http.request or nil,
        type(e)=="table" and type(e.fluxus)=="table" and e.fluxus.request or nil,
    }
    for _,f in ipairs(c) do if type(f)=="function" then return f end end
    return nil
end

local function exbLCQWRcjxU()
    local e=(getgenv and getgenv()) or _G
    local f=(e and e.identifyexecutor) or identifyexecutor or (e and e.getexecutorname) or getexecutorname
    if type(f)=="function" then
        local ok,a,b=pcall(f)
        if ok then return tostring(a or "unknown")..":"..tostring(b or "") end
    end
    return "unknown"
end

local function deMtEfINVhEd()
    local e=(getgenv and getgenv()) or _G
    local f=(e and e.gethwid) or gethwid
    if type(f)~="function" and type(e)=="table" and type(e.syn)=="table" then f=e.syn.gethwid end
    if type(f)=="function" then
        local ok,v=pcall(f)
        if ok and tostring(v or "")~="" then return "HWID:"..tostring(v) end
    end
    return "UID:"..tostring(lpRHXBpkBedf.UserId).."|EXEC:"..exbLCQWRcjxU()
end

local function polUAJKTylWH(path,obj)
    local r=reiuLwhSIJeZ()
    if not r then error("KIDz: executor HTTP request API required") end
    local ok,res=pcall(r,{
        Url=aphjYbPKcjFO..path, URL=aphjYbPKcjFO..path, Method="POST",
        Headers={["Content-Type"]="application/json",["Accept"]="application/json"},
        Body=hszLiosGIhcC:JSONEncode(obj),
    })
    if not ok then error("KIDz HTTP: "..tostring(res)) end
    local status=tonumber(res and (res.StatusCode or res.Status)) or 0
    local body=res and (res.Body or res.body or res.ResponseBody) or ""
    if status~=0 and (status<200 or status>=300) then
        local msg=tostring(body)
        pcall(function()
            local j=hszLiosGIhcC:JSONDecode(msg)
            if type(j)=="table" and j.error then msg=tostring(j.error) end
        end)
        error("KIDz: "..msg)
    end
    local okj,data=pcall(function() return hszLiosGIhcC:JSONDecode(tostring(body)) end)
    if not okj or type(data)~="table" then error("KIDz: invalid server response") end
    if data.ok~=true then error("KIDz: "..tostring(data.error or "request rejected")) end
    return data
end

local function poizINAlGcdS(path,obj)
    local r=reiuLwhSIJeZ()
    if not r then error("KIDz: executor HTTP request API required") end
    local ok,res=pcall(r,{
        Url=aphjYbPKcjFO..path, URL=aphjYbPKcjFO..path, Method="POST",
        Headers={["Content-Type"]="application/json",["Accept"]="text/plain"},
        Body=hszLiosGIhcC:JSONEncode(obj),
    })
    if not ok then error("KIDz HTTP: "..tostring(res)) end
    local status=tonumber(res and (res.StatusCode or res.Status)) or 0
    local body=res and (res.Body or res.body or res.ResponseBody) or ""
    if status~=0 and (status<200 or status>=300) then error("KIDz HTTP "..tostring(status)..": "..tostring(body)) end
    return tostring(body)
end

local b6SQrnaZfreZ="ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/"
local function b6iVaaREUwqb(s)
    s=tostring(s):gsub("[^"..b6SQrnaZfreZ.."=]","")
    local out={}
    local val,bits=0,0
    for i=1,#s do
        local ch=s:sub(i,i)
        if ch~="=" then
            local p=b6SQrnaZfreZ:find(ch,1,true)
            if not p then error("KIDz: base64 decode failed") end
            val=val*64+(p-1); bits=bits+6
            if bits>=8 then
                bits=bits-8
                local byte=math.floor(val/(2^bits))%256
                out[#out+1]=string.char(byte)
                val=val%(2^bits)
            end
        end
    end
    return table.concat(out)
end

local function hereYyIsqVUn(s)
    local out={}
    for i=1,#s,2 do
        local v=tonumber(s:sub(i,i+1),16)
        if not v then error("KIDz: hex decode failed") end
        out[#out+1]=string.char(v)
    end
    return table.concat(out)
end

local function u3nPDSjwdmzs(s,o)
    local a,b,c,d=s:byte(o,o+3)
    return a+b*256+c*65536+d*16777216
end

local function w3kJyXWwksmT(v)
    v=v%4294967296
    return string.char(v%256,math.floor(v/256)%256,math.floor(v/65536)%256,math.floor(v/16777216)%256)
end

local function rozTaVsPUpvA(v,n)
    return b3ncGiELGppM.bor(b3ncGiELGppM.lshift(v,n),b3ncGiELGppM.rshift(v,32-n))
end

local function qrHTVAxGrtLI(x,a,b,c,d)
    x[a]=b3ncGiELGppM.band(x[a]+x[b],0xffffffff); x[d]=rozTaVsPUpvA(b3ncGiELGppM.bxor(x[d],x[a]),16)
    x[c]=b3ncGiELGppM.band(x[c]+x[d],0xffffffff); x[b]=rozTaVsPUpvA(b3ncGiELGppM.bxor(x[b],x[c]),12)
    x[a]=b3ncGiELGppM.band(x[a]+x[b],0xffffffff); x[d]=rozTaVsPUpvA(b3ncGiELGppM.bxor(x[d],x[a]),8)
    x[c]=b3ncGiELGppM.band(x[c]+x[d],0xffffffff); x[b]=rozTaVsPUpvA(b3ncGiELGppM.bxor(x[b],x[c]),7)
end

local function chtksZorRqYm(data,key,nonce)
    if #key~=32 or #nonce~=12 then error("KIDz: cipher parameters invalid") end
    local const="expand 32-byte k"
    local cw={ u3nPDSjwdmzs(const,1),u3nPDSjwdmzs(const,5),u3nPDSjwdmzs(const,9),u3nPDSjwdmzs(const,13) }
    local kw={}
    for i=1,8 do kw[i]=u3nPDSjwdmzs(key,(i-1)*4+1) end
    local nw={ u3nPDSjwdmzs(nonce,1),u3nPDSjwdmzs(nonce,5),u3nPDSjwdmzs(nonce,9) }
    local out={}
    local off=1
    local counter=1
    while off<=#data do
        local st={cw[1],cw[2],cw[3],cw[4],kw[1],kw[2],kw[3],kw[4],kw[5],kw[6],kw[7],kw[8],counter,nw[1],nw[2],nw[3]}
        local x={}
        for i=1,16 do x[i]=st[i] end
        for _=1,10 do
            qrHTVAxGrtLI(x,1,5,9,13); qrHTVAxGrtLI(x,2,6,10,14); qrHTVAxGrtLI(x,3,7,11,15); qrHTVAxGrtLI(x,4,8,12,16)
            qrHTVAxGrtLI(x,1,6,11,16); qrHTVAxGrtLI(x,2,7,12,13); qrHTVAxGrtLI(x,3,8,9,14); qrHTVAxGrtLI(x,4,5,10,15)
        end
        local ks={}
        for i=1,16 do ks[#ks+1]=w3kJyXWwksmT(b3ncGiELGppM.band(x[i]+st[i],0xffffffff)) end
        local block=table.concat(ks)
        local take=math.min(64,#data-off+1)
        local z={}
        for i=1,take do z[i]=string.char(b3ncGiELGppM.bxor(data:byte(off+i-1),block:byte(i))) end
        out[#out+1]=table.concat(z)
        off=off+take
        counter=b3ncGiELGppM.band(counter+1,0xffffffff)
    end
    return table.concat(out)
end

local function lzUZRjkzsDto(blob)
    if #blob%2~=0 then error("KIDz: compressed payload invalid") end
    local d={}
    local function reset()
        d={}
        for i=0,255 do d[i]=string.char(i) end
    end
    reset()
    local nextCode=256
    local prev=nil
    local out={}
    local i=1
    while i<=#blob do
        local a,b=blob:byte(i,i+1); i=i+2
        local code=a*256+b
        if code==65535 then
            reset(); nextCode=256; prev=nil
        else
            local entry=d[code]
            if entry==nil and prev~=nil and code==nextCode then entry=prev..prev:sub(1,1) end
            if entry==nil then error("KIDz: decompression failed") end
            out[#out+1]=entry
            if prev~=nil and nextCode<=65534 then
                d[nextCode]=prev..entry:sub(1,1); nextCode=nextCode+1
            end
            prev=entry
        end
    end
    return table.concat(out)
end

local function adIEcAzseWoL(s)
    local a,b=1,0
    for i=1,#s do
        a=(a+s:byte(i))%65521
        b=(b+a)%65521
    end
    return b*65536+a
end

local seEmEtiYwwGi=polUAJKTylWH("/v1/session",{
    build_id=biJbCBXAGjyN,
    license_key=lidTLXpjdRNP,
    device_id=deMtEfINVhEd(),
    roblox_user_id=tostring(lpRHXBpkBedf.UserId),
    executor=exbLCQWRcjxU(),
})
local pakyyzXUBFWc=poizINAlGcdS("/v1/payload",{session_token=seEmEtiYwwGi.session_token})
local enAvhjZFiHOR=b6iVaaREUwqb(pakyyzXUBFWc)
local kenLSGNnjJKF=hereYyIsqVUn(seEmEtiYwwGi.key_hex)
local nozjUlrKfOHv=hereYyIsqVUn(seEmEtiYwwGi.nonce_hex)
local paaScFGzctev=chtksZorRqYm(enAvhjZFiHOR,kenLSGNnjJKF,nozjUlrKfOHv)
local srSrlrIJCwbK=lzUZRjkzsDto(paaScFGzctev)
if #(srSrlrIJCwbK)~=tonumber(seEmEtiYwwGi.source_size) then error("KIDz: payload size mismatch") end
if adIEcAzseWoL(srSrlrIJCwbK)~=tonumber(seEmEtiYwwGi.adler32) then error("KIDz: payload integrity mismatch") end
local fnnShhILbLVX,erViEtHetrtC=lsJxoMByWaao(srSrlrIJCwbK)
if not fnnShhILbLVX then error("KIDz compile: "..tostring(erViEtHetrtC)) end
return fnnShhILbLVX()
