
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Purchasing ERP - Quản lý mua hàng</title>
<style>
:root{
  --blue:#173a9e;--bg:#f3f6fb;--line:#dce4f0;
  --text:#17243c;--green:#087b55;--red:#c52b38
}
*{box-sizing:border-box}
body{margin:0;font-family:Arial,sans-serif;background:var(--bg);color:var(--text)}
header{background:linear-gradient(110deg,#102b77,#2463c6);color:white;padding:24px 5%}
header h1{margin:0;font-size:26px}
header p{margin:8px 0 0;color:#dce8ff}
nav{display:flex;gap:8px;flex-wrap:wrap;background:white;padding:12px 5%;border-bottom:1px solid var(--line)}
button{cursor:pointer;border:0;border-radius:7px;padding:11px 15px;font-weight:600}
nav button{background:#edf2fc;color:#244078}
nav button.active,.primary{background:var(--blue);color:white}
main{max-width:1400px;margin:auto;padding:25px}
.page{display:none}.page.active{display:block}
h2{margin-top:0}
.cards{display:grid;grid-template-columns:repeat(4,1fr);gap:15px}
.card,.panel{background:white;border:1px solid var(--line);border-radius:12px;padding:20px;margin-bottom:18px}
.card small{color:#65738b}
.card strong{display:block;font-size:28px;margin-top:12px;color:var(--blue)}
.grid{display:grid;grid-template-columns:repeat(4,1fr);gap:12px}
label{font-size:13px;font-weight:bold}
input,select{display:block;width:100%;margin-top:6px;padding:11px;border:1px solid #cbd5e1;border-radius:7px;background:white}
.actions{display:flex;gap:10px;margin-top:18px;flex-wrap:wrap}
.secondary{background:#e8edf5;color:#23375c}
.danger{background:#fff0f0;color:var(--red)}
.table-wrap{overflow-x:auto}
table{width:100%;border-collapse:collapse;min-width:1050px;font-size:13px}
th,td{padding:12px;text-align:left;border-bottom:1px solid var(--line)}
th{background:#edf3fc;color:#244078}
td button{padding:7px 10px;margin:2px}
.ok{color:var(--green);font-weight:bold}
.late{color:var(--red);font-weight:bold}
.warn{color:#a76a00;font-weight:bold}
.toolbar{display:flex;justify-content:space-between;align-items:center;gap:10px;flex-wrap:wrap;margin-bottom:15px}
.toolbar input{max-width:350px;margin:0}
.note{color:#68778d;font-size:13px}
@media(max-width:850px){
.cards,.grid{grid-template-columns:repeat(2,1fr)}
}
@media(max-width:500px){
.cards,.grid{grid-template-columns:1fr}
main{padding:12px}
}
</style>
</head>
<body>
<header>
<h1>PURCHASING ERP</h1>
<p>Hệ thống quản lý kế hoạch mua hàng và tiến độ cung ứng</p>
</header>

<nav>
<button class="active" onclick="showPage('dashboard',this)">Tổng quan</button>
<button onclick="showPage('plans',this)">Kế hoạch mua hàng</button>
<button onclick="showPage('orders',this)">Đơn đặt hàng</button>
<button onclick="showPage('suppliers',this)">Nhà cung cấp</button>
<button onclick="showPage('reports',this)">Báo cáo</button>
</nav>

<main>
<section id="dashboard" class="page active">
<h2>Tổng quan mua hàng</h2>
<div class="cards">
<div class="card"><small>Tổng đơn đặt hàng</small><strong id="totalOrders">0</strong></div>
<div class="card"><small>Tổng giá trị mua</small><strong id="totalValue">0</strong></div>
<div class="card"><small>Đơn chưa hoàn thành</small><strong id="pendingOrders">0</strong></div>
<div class="card"><small>Đơn quá hạn</small><strong id="lateOrders">0</strong></div>
</div>
<div class="panel">
<h3>Danh sách đơn hàng cần theo dõi</h3>
<div id="dashboardList"></div>
</div>
</section>

<section id="plans" class="page">
<h2>Kế hoạch mua hàng</h2>
<div class="panel">
<h3 id="planFormTitle">Thêm kế hoạch mua hàng</h3>
<form id="planForm">
<input type="hidden" id="planId">
<div class="grid">
<label>Dự án<input id="planProject" required></label>
<label>Tháng kế hoạch<input type="month" id="planMonth" required></label>
<label>Tuần kế hoạch<input type="number" id="planWeek" min="1" max="53" required></label>
<label>Mã vật tư<input id="planMaterialCode"></label>
<label>Tên vật tư<input id="planMaterial" required></label>
<label>Đơn vị tính<input id="planUnit" placeholder="Kg, tấn, bộ..." required></label>
<label>Số lượng cần mua<input type="number" id="planQty" min="0.001" step="any" required></label>
<label>Ngày cần hàng<input type="date" id="planDate" required></label>
</div>
<div class="actions">
<button class="primary" type="submit">Lưu kế hoạch</button>
<button class="secondary" type="reset" onclick="document.getElementById('planId').value=''">Làm mới</button>
</div>
</form>
</div>
<div class="panel">
<div class="toolbar">
<h3>Danh sách kế hoạch</h3>
<input id="planSearch" placeholder="Tìm dự án, vật tư..." oninput="renderPlans()">
</div>
<div class="table-wrap">
<table>
<thead><tr><th>Dự án</th><th>Tháng</th><th>Tuần</th><th>Mã VT</th><th>Vật tư</th><th>ĐVT</th><th>SL kế hoạch</th><th>Ngày cần</th><th>Thao tác</th></tr></thead>
<tbody id="planRows"></tbody>
</table>
</div>
</div>
</section>

<section id="orders" class="page">
<h2>Quản lý đơn đặt hàng</h2>
<div class="panel">
<h3>Thông tin đơn đặt hàng</h3>
<form id="orderForm">
<input type="hidden" id="orderId">
<div class="grid">
<label>Số đơn hàng<input id="poNumber" required></label>
<label>Dự án<input id="poProject" required></label>
<label>Nhà cung cấp<input id="poSupplier" required></label>
<label>Mã vật tư<input id="poCode"></label>
<label>Tên vật tư<input id="poMaterial" required></label>
<label>Đơn vị tính<input id="poUnit" required></label>
<label>Số lượng đặt<input id="poQty" type="number" min="0.001" step="any" required></label>
<label>Đơn giá (VNĐ)<input id="poPrice" type="number" min="0" step="any" required></label>
<label>Số lượng đã giao<input id="poDelivered" type="number" min="0" step="any" value="0" required></label>
<label>Ngày đặt hàng<input id="poDate" type="date" required></label>
<label>Ngày cam kết giao<input id="poDeliveryDate" type="date" required></label>
<label>Ghi chú<input id="poNote"></label>
</div>
<div class="actions">
<button class="primary" type="submit">Lưu đơn hàng</button>
<button class="secondary" type="reset" onclick="document.getElementById('orderId').value=''">Làm mới</button>
</div>
</form>
</div>
<div class="panel">
<div class="toolbar">
<h3>Danh sách đơn hàng</h3>
<input id="orderSearch" placeholder="Tìm PO, dự án, nhà cung cấp..." oninput="renderOrders()">
</div>
<div class="table-wrap">
<table>
<thead><tr><th>Số PO</th><th>Dự án</th><th>NCC</th><th>Vật tư</th><th>SL đặt</th><th>Đã giao</th><th>Còn thiếu</th><th>Giá trị</th><th>Ngày giao</th><th>Trạng thái</th><th>Thao tác</th></tr></thead>
<tbody id="orderRows"></tbody>
</table>
</div>
</div>
</section>

<section id="suppliers" class="page">
<h2>Danh mục nhà cung cấp</h2>
<div class="panel">
<form id="supplierForm">
<input type="hidden" id="supplierId">
<div class="grid">
<label>Mã NCC<input id="supplierCode" required></label>
<label>Tên nhà cung cấp<input id="supplierName" required></label>
<label>Điện thoại<input id="supplierPhone"></label>
<label>Nhóm hàng cung cấp<input id="supplierGroup"></label>
</div>
<div class="actions">
<button class="primary">Lưu nhà cung cấp</button>
</div>
</form>
</div>
<div class="panel table-wrap">
<table>
<thead><tr><th>Mã NCC</th><th>Tên NCC</th><th>Điện thoại</th><th>Nhóm hàng</th><th>Thao tác</th></tr></thead>
<tbody id="supplierRows"></tbody>
</table>
</div>
</section>

<section id="reports" class="page">
<h2>Báo cáo mua hàng</h2>
<div class="cards">
<div class="card"><small>Giá trị đặt mua</small><strong id="reportValue">0</strong></div>
<div class="card"><small>Giá trị đã giao</small><strong id="reportDelivered">0</strong></div>
<div class="card"><small>Giá trị chưa giao</small><strong id="reportRemaining">0</strong></div>
<div class="card"><small>Tỷ lệ đáp ứng</small><strong id="reportRate">0%</strong></div>
</div>
<div class="panel">
<h3>Xuất dữ liệu và sao lưu</h3>
<div class="actions">
<button class="primary" onclick="exportCSV()">Xuất báo cáo CSV</button>
<button class="secondary" onclick="backupJSON()">Sao lưu JSON</button>
<label>Khôi phục JSON
<input type="file" accept=".json" onchange="restoreJSON(event)">
</label>
</div>
<p class="note">CSV mở được bằng Excel. Dữ liệu được lưu trong trình duyệt đang sử dụng.</p>
</div>
</section>
</main>

<script>
const STORE="purchasing_erp_v1";
let db=loadDB();

function loadDB(){
 try{
  const data=JSON.parse(localStorage.getItem(STORE));
  if(data&&Array.isArray(data.plans)&&Array.isArray(data.orders)&&Array.isArray(data.suppliers))return data;
 }catch(e){}
 return {plans:[],orders:[],suppliers:[]};
}
function save(){
 localStorage.setItem(STORE,JSON.stringify(db));
 renderAll();
}
function uid(){return crypto.randomUUID?crypto.randomUUID():String(Date.now())+Math.random()}
function val(id){return document.getElementById(id).value.trim()}
function setVal(id,v){document.getElementById(id).value=v??""}
function money(n){return Number(n||0).toLocaleString("vi-VN")}
function esc(s){
 return String(s??"").replace(/[&<>"']/g,c=>({
 "&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"
 })[c]);
}
function showPage(id,button){
 document.querySelectorAll(".page").forEach(x=>x.classList.remove("active"));
 document.getElementById(id).classList.add("active");
 document.querySelectorAll("nav button").forEach(x=>x.classList.remove("active"));
 button.classList.add("active");
 renderAll();
}
function status(o){
 const qty=Number(o.qty),del=Number(o.delivered);
 if(del>=qty)return ["Hoàn thành","ok"];
 const today=new Date().toISOString().slice(0,10);
 if(o.deliveryDate<today)return ["Quá hạn","late"];
 if(del>0)return ["Giao một phần","warn"];
 return ["Chưa giao","warn"];
}
function rowActions(type,id){
 return `<button class="secondary" onclick="editRecord('${type}','${id}')">Sửa</button>
 <button class="danger" onclick="deleteRecord('${type}','${id}')">Xóa</button>`;
}

document.getElementById("planForm").onsubmit=e=>{
 e.preventDefault();
 const id=val("planId")||uid();
 const item={
 id,project:val("planProject"),month:val("planMonth"),
 week:val("planWeek"),code:val("planMaterialCode"),
 material:val("planMaterial"),unit:val("planUnit"),
 qty:Number(val("planQty")),date:val("planDate")
 };
 const i=db.plans.findIndex(x=>x.id===id);
 if(i>=0)db.plans[i]=item;else db.plans.push(item);
 e.target.reset();setVal("planId","");
 save();alert("Đã lưu kế hoạch");
};

document.getElementById("orderForm").onsubmit=e=>{
 e.preventDefault();
 const qty=Number(val("poQty")),del=Number(val("poDelivered"));
 if(del>qty){alert("Số lượng đã giao không được vượt số lượng đặt");return}
 const id=val("orderId")||uid();
 const item={
 id,number:val("poNumber"),project:val("poProject"),
 supplier:val("poSupplier"),code:val("poCode"),
 material:val("poMaterial"),unit:val("poUnit"),
 qty,price:Number(val("poPrice")),delivered:del,
 date:val("poDate"),deliveryDate:val("poDeliveryDate"),
 note:val("poNote")
 };
 const i=db.orders.findIndex(x=>x.id===id);
 if(i>=0)db.orders[i]=item;else db.orders.push(item);
 e.target.reset();setVal("orderId","");
 save();alert("Đã lưu đơn hàng");
};

document.getElementById("supplierForm").onsubmit=e=>{
 e.preventDefault();
 const id=val("supplierId")||uid();
 const item={
 id,code:val("supplierCode"),name:val("supplierName"),
 phone:val("supplierPhone"),group:val("supplierGroup")
 };
 const i=db.suppliers.findIndex(x=>x.id===id);
 if(i>=0)db.suppliers[i]=item;else db.suppliers.push(item);
 e.target.reset();setVal("supplierId","");
 save();alert("Đã lưu nhà cung cấp");
};

function renderPlans(){
 const q=val("planSearch").toLowerCase();
 const items=db.plans.filter(x=>
 [x.project,x.material,x.code].join(" ").toLowerCase().includes(q));
 document.getElementById("planRows").innerHTML=items.map(x=>`
 <tr><td>${esc(x.project)}</td><td>${esc(x.month)}</td>
 <td>${esc(x.week)}</td><td>${esc(x.code)}</td>
 <td>${esc(x.material)}</td><td>${esc(x.unit)}</td>
 <td>${money(x.qty)}</td><td>${esc(x.date)}</td>
 <td>${rowActions("plans",x.id)}</td></tr>`).join("");
}

function renderOrders(){
 const q=val("orderSearch").toLowerCase();
 const items=db.orders.filter(x=>
 [x.number,x.project,x.supplier,x.material].join(" ").toLowerCase().includes(q));
 document.getElementById("orderRows").innerHTML=items.map(x=>{
 const s=status(x);
 return `<tr><td>${esc(x.number)}</td><td>${esc(x.project)}</td>
 <td>${esc(x.supplier)}</td><td>${esc(x.material)}</td>
 <td>${money(x.qty)}</td><td>${money(x.delivered)}</td>
 <td>${money(Math.max(0,x.qty-x.delivered))}</td>
 <td>${money(x.qty*x.price)}</td><td>${esc(x.deliveryDate)}</td>
 <td class="${s[1]}">${s[0]}</td>
 <td>${rowActions("orders",x.id)}</td></tr>`;
 }).join("");
}

function renderSuppliers(){
 document.getElementById("supplierRows").innerHTML=db.suppliers.map(x=>`
 <tr><td>${esc(x.code)}</td><td>${esc(x.name)}</td>
 <td>${esc(x.phone)}</td><td>${esc(x.group)}</td>
 <td>${rowActions("suppliers",x.id)}</td></tr>`).join("");
}

function editRecord(type,id){
 const x=db[type].find(a=>a.id===id);
 if(!x)return;
 const map={
 plans:{planId:"id",planProject:"project",planMonth:"month",
 planWeek:"week",planMaterialCode:"code",planMaterial:"material",
 planUnit:"unit",planQty:"qty",planDate:"date"},
 orders:{orderId:"id",poNumber:"number",poProject:"project",
 poSupplier:"supplier",poCode:"code",poMaterial:"material",
 poUnit:"unit",poQty:"qty",poPrice:"price",
 poDelivered:"delivered",poDate:"date",
 poDeliveryDate:"deliveryDate",poNote:"note"},
 suppliers:{supplierId:"id",supplierCode:"code",
 supplierName:"name",supplierPhone:"phone",supplierGroup:"group"}
 };
 Object.entries(map[type]).forEach(([field,key])=>setVal(field,x[key]));
 const page={plans:"plans",orders:"orders",suppliers:"suppliers"}[type];
 document.querySelector(`nav button[onclick*="'${page}'"]`).click();
 window.scrollTo(0,0);
}
function deleteRecord(type,id){
 if(!confirm("Bạn chắc chắn muốn xóa dữ liệu này?"))return;
 db[type]=db[type].filter(x=>x.id!==id);
 save();
}

function renderDashboard(){
 const total=db.orders.reduce((s,x)=>s+x.qty*x.price,0);
 const pending=db.orders.filter(x=>x.delivered<x.qty);
 const late=pending.filter(x=>status(x)[0]==="Quá hạn");
 document.getElementById("totalOrders").textContent=db.orders.length;
 document.getElementById("totalValue").textContent=money(total)+" đ";
 document.getElementById("pendingOrders").textContent=pending.length;
 document.getElementById("lateOrders").textContent=late.length;
 document.getElementById("dashboardList").innerHTML=
 pending.length?pending.map(x=>`<p>${esc(x.number)} - ${esc(x.project)}
 - ${esc(x.material)}: <b class="${status(x)[1]}">${status(x)[0]}</b></p>`).join("")
 :'<p class="note">Không có đơn hàng chưa hoàn thành.</p>';
}
function renderReports(){
 const total=db.orders.reduce((s,x)=>s+x.qty*x.price,0);
 const delivered=db.orders.reduce((s,x)=>s+x.delivered*x.price,0);
 document.getElementById("reportValue").textContent=money(total)+" đ";
 document.getElementById("reportDelivered").textContent=money(delivered)+" đ";
 document.getElementById("reportRemaining").textContent=money(total-delivered)+" đ";
 document.getElementById("reportRate").textContent=
 total?(delivered/total*100).toFixed(1)+"%":"0%";
}
function renderAll(){
 renderPlans();renderOrders();renderSuppliers();
 renderDashboard();renderReports();
}
function download(name,content,type){
 const blob=new Blob([content],{type});
 const url=URL.createObjectURL(blob);
 const a=document.createElement("a");
 a.href=url;a.download=name;a.click();
 setTimeout(()=>URL.revokeObjectURL(url),1000);
}
function exportCSV(){
 const headers=["So PO","Du an","NCC","Ma VT","Vat tu",
 "DVT","SL dat","SL giao","Con thieu","Don gia",
 "Gia tri","Ngay dat","Ngay giao","Trang thai"];
 const rows=db.orders.map(x=>[
 x.number,x.project,x.supplier,x.code,x.material,x.unit,
 x.qty,x.delivered,x.qty-x.delivered,x.price,
 x.qty*x.price,x.date,x.deliveryDate,status(x)[0]
 ]);
 const csv=[headers,...rows].map(row=>row.map(v=>
 '"'+String(v??"").replace(/"/g,'""')+'"').join(",")).join("\r\n");
 download("Bao_cao_mua_hang.csv","\uFEFF"+csv,"text/csv;charset=utf-8");
}
function backupJSON(){
 download("Du_lieu_mua_hang.json",JSON.stringify(db,null,2),"application/json");
}
function restoreJSON(e){
 const file=e.target.files[0];if(!file)return;
 const reader=new FileReader();
 reader.onload=()=>{
 try{
 const data=JSON.parse(reader.result);
 if(!Array.isArray(data.plans)||!Array.isArray(data.orders)||
 !Array.isArray(data.suppliers))throw Error("Sai cấu trúc");
 if(!confirm("Khôi phục sẽ thay thế dữ liệu hiện tại. Tiếp tục?"))return;
 db=data;save();alert("Đã khôi phục dữ liệu");
 }catch(err){alert("File JSON không hợp lệ")}
 };
 reader.readAsText(file);
}
renderAll();
</script>
</body>
</html>

