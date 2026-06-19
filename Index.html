cat > /mnt/user-data/outputs/index.html << 'HTMLEOF'
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>FloorMatch</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/react/18.2.0/umd/react.production.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/react-dom/18.2.0/umd/react-dom.production.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/7.23.2/babel.min.js"></script>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { background: linear-gradient(135deg, #f0faf8 0%, #e8f4f8 100%); min-height: 100vh; font-family: 'Segoe UI', system-ui, sans-serif; }
  </style>
</head>
<body>
  <div id="root"></div>
  <script type="text/babel">
    const { useState, useRef } = React;

    function hexToRgb(hex) {
      const clean = hex.replace("#", "");
      return { r: parseInt(clean.slice(0,2),16), g: parseInt(clean.slice(2,4),16), b: parseInt(clean.slice(4,6),16) };
    }
    function rgbToHex(r,g,b) {
      return "#" + [r,g,b].map(v => Math.max(0,Math.min(255,Math.round(v))).toString(16).padStart(2,"0")).join("");
    }
    function colorDistance(h1,h2) {
      const a=hexToRgb(h1), b=hexToRgb(h2);
      return Math.sqrt((a.r-b.r)**2+(a.g-b.g)**2+(a.b-b.b)**2);
    }
    function extractDominantColor(el) {
      const c=document.createElement("canvas"); c.width=c.height=80;
      const ctx=c.getContext("2d"); ctx.drawImage(el,0,0,80,80);
      const d=ctx.getImageData(0,0,80,80).data;
      let r=0,g=0,b=0,n=0;
      for(let i=0;i<d.length;i+=4){r+=d[i];g+=d[i+1];b+=d[i+2];n++;}
      return rgbToHex(r/n,g/n,b/n);
    }

    const INITIAL_PRODUCTS = [
      {id:1,name:"Oak Elegance",code:"FL-001",color:"#c8a46e",price:85,qty:120,type:"Flooring",img:null},
      {id:2,name:"Ivory Dream",code:"CP-002",color:"#e8d5b0",price:65,qty:80,type:"Carpet",img:null},
      {id:3,name:"Slate Stone",code:"FL-003",color:"#7a7d80",price:110,qty:45,type:"Flooring",img:null},
      {id:4,name:"Warm Walnut",code:"FL-004",color:"#8b5e3c",price:95,qty:60,type:"Flooring",img:null},
      {id:5,name:"Sand Dune",code:"CP-005",color:"#d4b483",price:55,qty:200,type:"Carpet",img:null},
      {id:6,name:"Midnight Ash",code:"FL-006",color:"#3a3a3a",price:130,qty:30,type:"Flooring",img:null},
      {id:7,name:"Blush Beige",code:"CP-007",color:"#e0c9b0",price:70,qty:90,type:"Carpet",img:null},
      {id:8,name:"Terracotta",code:"FL-008",color:"#b85c38",price:100,qty:55,type:"Flooring",img:null},
    ];

    function Swatch({color,size=40}) {
      return <div style={{width:size,height:size,borderRadius:8,background:color,border:"2px solid rgba(0,0,0,0.12)",flexShrink:0}} />;
    }

    function Badge({pct}) {
      const c = pct>=90?"#22c55e":pct>=70?"#f59e0b":"#94a3b8";
      return <span style={{background:c+"22",color:c,border:`1px solid ${c}66`,borderRadius:20,padding:"2px 10px",fontSize:12,fontWeight:700}}>{pct}% match</span>;
    }

    function ProductCard({product,matchPct,onDelete}) {
      const [confirm,setConfirm]=useState(false);
      return (
        <div style={{background:"#fff",borderRadius:14,boxShadow:"0 2px 12px rgba(0,0,0,0.08)",padding:16,display:"flex",gap:14,alignItems:"center",border:matchPct>=90?"2px solid #22c55e44":"2px solid transparent"}}>
          {product.img ? <img src={product.img} alt={product.name} style={{width:60,height:60,borderRadius:10,objectFit:"cover",flexShrink:0}}/> : <Swatch color={product.color} size={60}/>}
          <div style={{flex:1,minWidth:0}}>
            <div style={{display:"flex",justifyContent:"space-between",alignItems:"flex-start",gap:8}}>
              <span style={{fontWeight:700,fontSize:15,color:"#1e293b"}}>{product.name}</span>
              {matchPct!=null && <Badge pct={matchPct}/>}
            </div>
            <div style={{fontSize:12,color:"#64748b",marginTop:3}}>{product.code} · {product.type}</div>
            <div style={{display:"flex",gap:16,marginTop:6}}>
              <span style={{fontSize:13,fontWeight:600,color:"#0f766e"}}>${product.price}/m²</span>
              <span style={{fontSize:13,color:product.qty>50?"#16a34a":"#dc2626"}}>{product.qty>0?`${product.qty} m² in stock`:"Out of stock"}</span>
            </div>
            {onDelete && (
              <div style={{marginTop:8}}>
                {!confirm
                  ? <button onClick={()=>setConfirm(true)} style={{background:"none",border:"1px solid #fca5a5",color:"#dc2626",borderRadius:8,padding:"4px 12px",fontSize:12,fontWeight:600,cursor:"pointer"}}>🗑 Delete</button>
                  : <div style={{display:"flex",gap:8}}>
                      <button onClick={()=>onDelete(product.id)} style={{background:"#dc2626",color:"#fff",border:"none",borderRadius:8,padding:"4px 12px",fontSize:12,fontWeight:600,cursor:"pointer"}}>Yes, delete</button>
                      <button onClick={()=>setConfirm(false)} style={{background:"#f1f5f9",color:"#475569",border:"1px solid #e2e8f0",borderRadius:8,padding:"4px 12px",fontSize:12,fontWeight:600,cursor:"pointer"}}>Cancel</button>
                    </div>
                }
              </div>
            )}
          </div>
          <Swatch color={product.color} size={32}/>
        </div>
      );
    }

    function ScanView({products,onBack}) {
      const videoRef=useRef(null), canvasRef=useRef(null), fileRef=useRef(null);
      const [streaming,setStreaming]=useState(false);
      const [scannedColor,setScannedColor]=useState(null);
      const [results,setResults]=useState(null);
      const [uploadedImg,setUploadedImg]=useState(null);

      const startCamera=async()=>{
        try {
          const s=await navigator.mediaDevices.getUserMedia({video:{facingMode:"environment"}});
          videoRef.current.srcObject=s; videoRef.current.play(); setStreaming(true);
        } catch { alert("Please allow camera access in your browser settings."); }
      };
      const stopCamera=()=>{
        if(videoRef.current?.srcObject) videoRef.current.srcObject.getTracks().forEach(t=>t.stop());
        if(videoRef.current) videoRef.current.srcObject=null;
        setStreaming(false);
      };
      const capture=()=>{
        const v=videoRef.current,c=canvasRef.current;
        c.width=v.videoWidth; c.height=v.videoHeight;
        c.getContext("2d").drawImage(v,0,0);
        analyze(extractDominantColor(v)); stopCamera();
      };
      const handleUpload=e=>{
        const f=e.target.files[0]; if(!f) return;
        const url=URL.createObjectURL(f);
        const img=new Image();
        img.onload=()=>{ setUploadedImg(url); analyze(extractDominantColor(img)); };
        img.src=url;
      };
      const analyze=color=>{
        setScannedColor(color);
        setResults(products.map(p=>({...p,pct:Math.round(Math.max(0,100-(colorDistance(color,p.color)/441)*100))})).sort((a,b)=>b.pct-a.pct).slice(0,5));
      };
      const reset=()=>{ setScannedColor(null); setResults(null); setUploadedImg(null); stopCamera(); };

      const btn={background:"linear-gradient(135deg,#0f766e,#0d9488)",color:"#fff",border:"none",borderRadius:12,padding:"14px 20px",fontSize:15,fontWeight:600,cursor:"pointer",width:"100%",boxShadow:"0 3px 14px rgba(15,118,110,0.3)"};
      const btn2={background:"#f1f5f9",color:"#475569",border:"1px solid #e2e8f0",borderRadius:12,padding:"13px 20px",fontSize:15,fontWeight:600,cursor:"pointer",width:"100%"};

      return (
        <div>
          <button onClick={onBack} style={{background:"none",border:"none",color:"#0f766e",fontSize:15,fontWeight:600,cursor:"pointer",padding:"0 0 12px"}}>← Back</button>
          <h2 style={{fontSize:20,fontWeight:800,color:"#1e293b",marginBottom:16}}>Color Match</h2>
          {!results ? (
            <div>
              {!streaming ? (
                <div style={{display:"flex",flexDirection:"column",gap:12}}>
                  <button onClick={startCamera} style={btn}>📸 Open Camera</button>
                  <button onClick={()=>fileRef.current.click()} style={btn2}>🖼️ Upload Sample Image</button>
                  <input ref={fileRef} type="file" accept="image/*" style={{display:"none"}} onChange={handleUpload}/>
                </div>
              ) : (
                <div>
                  <video ref={videoRef} style={{width:"100%",borderRadius:14,background:"#000"}} playsInline/>
                  <canvas ref={canvasRef} style={{display:"none"}}/>
                  <div style={{display:"flex",gap:10,marginTop:10}}>
                    <button onClick={capture} style={{...btn,flex:1}}>📷 Capture</button>
                    <button onClick={stopCamera} style={{...btn2,flex:1}}>Cancel</button>
                  </div>
                </div>
              )}
              {uploadedImg && <img src={uploadedImg} alt="sample" style={{width:"100%",borderRadius:14,marginTop:12}}/>}
            </div>
          ) : (
            <div>
              <div style={{background:"#fff",borderRadius:14,padding:16,marginBottom:16,boxShadow:"0 2px 12px rgba(0,0,0,0.08)",display:"flex",alignItems:"center",gap:14}}>
                <Swatch color={scannedColor} size={52}/>
                <div>
                  <div style={{fontSize:13,color:"#64748b"}}>Extracted color from sample</div>
                  <div style={{fontWeight:700,fontSize:16,color:"#1e293b",marginTop:2}}>{scannedColor.toUpperCase()}</div>
                </div>
              </div>
              <h3 style={{fontSize:15,fontWeight:700,color:"#475569",marginBottom:12}}>Closest matches in stock</h3>
              <div style={{display:"flex",flexDirection:"column",gap:10}}>
                {results.map(p=><ProductCard key={p.id} product={p} matchPct={p.pct}/>)}
              </div>
              <button onClick={reset} style={{...btn2,marginTop:16}}>🔄 New Scan</button>
            </div>
          )}
        </div>
      );
    }

    function InventoryView({products,onBack,onDelete}) {
      const [filter,setFilter]=useState("All");
      const filtered=filter==="All"?products:products.filter(p=>p.type===filter);
      const fa={background:"#0f766e",color:"#fff",border:"none",borderRadius:20,padding:"7px 16px",fontSize:13,fontWeight:600,cursor:"pointer"};
      const fi={background:"#f1f5f9",color:"#475569",border:"1px solid #e2e8f0",borderRadius:20,padding:"7px 16px",fontSize:13,fontWeight:600,cursor:"pointer"};
      return (
        <div>
          <button onClick={onBack} style={{background:"none",border:"none",color:"#0f766e",fontSize:15,fontWeight:600,cursor:"pointer",padding:"0 0 12px"}}>← Back</button>
          <h2 style={{fontSize:20,fontWeight:800,color:"#1e293b",marginBottom:16}}>Inventory ({products.length} products)</h2>
          <div style={{display:"flex",gap:8,marginBottom:16}}>
            {["All","Flooring","Carpet"].map(t=><button key={t} onClick={()=>setFilter(t)} style={filter===t?fa:fi}>{t}</button>)}
          </div>
          <div style={{display:"flex",flexDirection:"column",gap:10}}>
            {filtered.map(p=><ProductCard key={p.id} product={p} onDelete={onDelete}/>)}
          </div>
        </div>
      );
    }

    function AddProductView({onAdd,onBack}) {
      const [form,setForm]=useState({name:"",code:"",color:"#c8a46e",price:"",qty:"",type:"Flooring"});
      const [imgPreview,setImgPreview]=useState(null);
      const [streaming,setStreaming]=useState(false);
      const videoRef=useRef(null), canvasRef=useRef(null);
      const set=(k,v)=>setForm(f=>({...f,[k]:v}));

      const startCamera=async()=>{
        try {
          const s=await navigator.mediaDevices.getUserMedia({video:{facingMode:"environment"}});
          videoRef.current.srcObject=s; videoRef.current.play(); setStreaming(true);
        } catch { alert("Please allow camera access."); }
      };
      const stopCamera=()=>{
        if(videoRef.current?.srcObject) videoRef.current.srcObject.getTracks().forEach(t=>t.stop());
        if(videoRef.current) videoRef.current.srcObject=null;
        setStreaming(false);
      };
      const capturePhoto=()=>{
        const v=videoRef.current,c=canvasRef.current;
        c.width=v.videoWidth; c.height=v.videoHeight;
        c.getContext("2d").drawImage(v,0,0);
        setImgPreview(c.toDataURL("image/jpeg",0.8)); stopCamera();
      };
      const submit=()=>{
        if(!form.name||!form.code||!form.price||!form.qty){alert("Please fill in all required fields.");return;}
        onAdd({...form,price:+form.price,qty:+form.qty,img:imgPreview});
      };

      const btn={background:"linear-gradient(135deg,#0f766e,#0d9488)",color:"#fff",border:"none",borderRadius:12,padding:"14px 20px",fontSize:15,fontWeight:600,cursor:"pointer",width:"100%",boxShadow:"0 3px 14px rgba(15,118,110,0.3)"};
      const btn2={background:"#f1f5f9",color:"#475569",border:"1px solid #e2e8f0",borderRadius:12,padding:"13px 20px",fontSize:15,fontWeight:600,cursor:"pointer",width:"100%"};
      const inp={width:"100%",padding:"12px 14px",borderRadius:10,border:"1.5px solid #e2e8f0",fontSize:14,color:"#1e293b",outline:"none",boxSizing:"border-box",background:"#fff"};
      const lbl={display:"block",fontSize:13,fontWeight:600,color:"#475569",marginBottom:6};

      return (
        <div>
          <button onClick={onBack} style={{background:"none",border:"none",color:"#0f766e",fontSize:15,fontWeight:600,cursor:"pointer",padding:"0 0 12px"}}>← Back</button>
          <h2 style={{fontSize:20,fontWeight:800,color:"#1e293b",marginBottom:16}}>Add New Product</h2>
          <div style={{display:"flex",flexDirection:"column",gap:14}}>

            <div>
              <label style={lbl}>Product Photo</label>
              {!streaming && !imgPreview && <button onClick={startCamera} style={btn2}>📸 Take Photo with Camera</button>}
              {streaming && (
                <div>
                  <video ref={videoRef} style={{width:"100%",borderRadius:14,background:"#000"}} playsInline/>
                  <canvas ref={canvasRef} style={{display:"none"}}/>
                  <div style={{display:"flex",gap:10,marginTop:10}}>
                    <button onClick={capturePhoto} style={{...btn,flex:1}}>📷 Capture</button>
                    <button onClick={stopCamera} style={{...btn2,flex:1}}>Cancel</button>
                  </div>
                </div>
              )}
              {imgPreview && !streaming && (
                <div>
                  <img src={imgPreview} alt="preview" style={{width:"100%",height:160,objectFit:"cover",borderRadius:14,border:"2px solid #e2e8f0"}}/>
                  <button onClick={startCamera} style={{...btn2,marginTop:8}}>🔄 Retake Photo</button>
                </div>
              )}
            </div>

            {[{label:"Product Name",key:"name",ph:"e.g. Oak Elegance"},{label:"Color Code",key:"code",ph:"e.g. FL-001"},{label:"Price ($/m²)",key:"price",ph:"85",t:"number"},{label:"Quantity in Stock (m²)",key:"qty",ph:"100",t:"number"}].map(({label,key,ph,t})=>(
              <div key={key}>
                <label style={lbl}>{label}</label>
                <input type={t||"text"} placeholder={ph} value={form[key]} onChange={e=>set(key,e.target.value)} style={inp}/>
              </div>
            ))}

            <div>
              <label style={lbl}>Type</label>
              <div style={{display:"flex",gap:10}}>
                {["Flooring","Carpet"].map(t=>(
                  <button key={t} onClick={()=>set("type",t)} style={form.type===t?{background:"#0f766e",color:"#fff",border:"none",borderRadius:20,padding:"7px 16px",fontSize:13,fontWeight:600,cursor:"pointer"}:{background:"#f1f5f9",color:"#475569",border:"1px solid #e2e8f0",borderRadius:20,padding:"7px 16px",fontSize:13,fontWeight:600,cursor:"pointer"}}>{t}</button>
                ))}
              </div>
            </div>

            <div>
              <label style={lbl}>Product Color</label>
              <div style={{display:"flex",gap:12,alignItems:"center"}}>
                <input type="color" value={form.color} onChange={e=>set("color",e.target.value)} style={{width:52,height:52,border:"none",borderRadius:10,cursor:"pointer",padding:2}}/>
                <span style={{color:"#475569",fontSize:14}}>{form.color.toUpperCase()}</span>
              </div>
            </div>

            <button onClick={submit} style={{...btn,marginTop:4}}>✅ Save Product</button>
          </div>
        </div>
      );
    }

    function App() {
      const [products,setProducts]=useState(INITIAL_PRODUCTS);
      const [view,setView]=useState("home");
      const [addedMsg,setAddedMsg]=useState(false);
      const [deletedMsg,setDeletedMsg]=useState(false);

      const addProduct=p=>{ setProducts(prev=>[...prev,{...p,id:Date.now()}]); setAddedMsg(true); setTimeout(()=>setAddedMsg(false),2500); setView("home"); };
      const deleteProduct=id=>{ setProducts(prev=>prev.filter(p=>p.id!==id)); setDeletedMsg(true); setTimeout(()=>setDeletedMsg(false),2500); };

      const toast={position:"fixed",top:20,left:"50%",transform:"translateX(-50%)",color:"#fff",borderRadius:12,padding:"12px 24px",fontSize:14,fontWeight:600,boxShadow:"0 4px 20px rgba(0,0,0,0.2)",zIndex:999,whiteSpace:"nowrap"};

      return (
        <div style={{minHeight:"100vh",background:"linear-gradient(135deg,#f0faf8 0%,#e8f4f8 100%)",fontFamily:"'Segoe UI',system-ui,sans-serif"}}>
          <div style={{maxWidth:480,margin:"0 auto",padding:"20px 16px 40px",position:"relative"}}>

            {addedMsg && <div style={{...toast,background:"#0f766e"}}>✅ Product added successfully!</div>}
            {deletedMsg && <div style={{...toast,background:"#dc2626"}}>🗑 Product deleted.</div>}

            {view==="home" && (
              <div>
                <div style={{display:"flex",gap:12,alignItems:"center",marginBottom:20}}>
                  <div style={{fontSize:28}}>🪵</div>
                  <div>
                    <h1 style={{fontSize:26,fontWeight:800,color:"#0f766e",margin:0,lineHeight:1}}>FloorMatch</h1>
                    <p style={{fontSize:13,color:"#64748b",margin:"3px 0 0"}}>Instant Color Matching</p>
                  </div>
                </div>

                <div style={{display:"flex",gap:10,marginBottom:16}}>
                  {[["Products",products.length],["Flooring",products.filter(p=>p.type==="Flooring").length],["Carpet",products.filter(p=>p.type==="Carpet").length]].map(([l,n])=>(
                    <div key={l} style={{flex:1,background:"#fff",borderRadius:12,padding:"12px 8px",textAlign:"center",boxShadow:"0 1px 8px rgba(0,0,0,0.06)"}}>
                      <div style={{fontSize:22,fontWeight:800,color:"#0f766e"}}>{n}</div>
                      <div style={{fontSize:11,color:"#94a3b8",marginTop:2}}>{l}</div>
                    </div>
                  ))}
                </div>

                <div style={{display:"flex",flexDirection:"column",gap:12,marginTop:8}}>
                  <button onClick={()=>setView("scan")} style={{background:"linear-gradient(135deg,#0f766e,#0d9488)",color:"#fff",border:"none",borderRadius:16,padding:"18px 20px",cursor:"pointer",display:"flex",alignItems:"center",gap:16,boxShadow:"0 4px 20px rgba(15,118,110,0.35)",textAlign:"left",width:"100%"}}>
                    <span style={{fontSize:28}}>📸</span>
                    <div>
                      <div style={{fontWeight:700,fontSize:17}}>Match a Sample</div>
                      <div style={{fontSize:13,opacity:0.8,marginTop:2}}>Scan or photo a sample to find the closest match</div>
                    </div>
                  </button>
                  <div style={{display:"flex",gap:12}}>
                    <button onClick={()=>setView("inventory")} style={{background:"#1e293b",color:"#fff",border:"none",borderRadius:14,padding:"16px 12px",cursor:"pointer",display:"flex",flexDirection:"column",alignItems:"center",boxShadow:"0 2px 12px rgba(0,0,0,0.15)",flex:1}}>
                      <span style={{fontSize:22}}>📦</span>
                      <div style={{fontSize:14,fontWeight:600,marginTop:4}}>Inventory</div>
                    </button>
                    <button onClick={()=>setView("add")} style={{background:"#0f766e",color:"#fff",border:"none",borderRadius:14,padding:"16px 12px",cursor:"pointer",display:"flex",flexDirection:"column",alignItems:"center",boxShadow:"0 2px 12px rgba(0,0,0,0.15)",flex:1}}>
                      <span style={{fontSize:22}}>➕</span>
                      <div style={{fontSize:14,fontWeight:600,marginTop:4}}>Add Product</div>
                    </button>
                  </div>
                </div>

                <h3 style={{fontSize:15,fontWeight:700,color:"#475569",margin:"20px 0 10px"}}>Recent Products</h3>
                <div style={{display:"flex",flexDirection:"column",gap:8}}>
                  {products.slice(-3).reverse().map(p=><ProductCard key={p.id} product={p}/>)}
                </div>
              </div>
            )}

            {view==="scan" && <ScanView products={products} onBack={()=>setView("home")}/>}
            {view==="inventory" && <InventoryView products={products} onBack={()=>setView("home")} onDelete={deleteProduct}/>}
            {view==="add" && <AddProductView onAdd={addProduct} onBack={()=>setView("home")}/>}
          </div>
        </div>
      );
    }

    ReactDOM.createRoot(document.getElementById("root")).render(<App/>);
  </script>
</body>
</html>
HTMLEOF
echo "Done"
