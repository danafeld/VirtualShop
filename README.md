 Read Me

פרטים בסיסים:
ישנם שתי מחלקות שמכילות את כל הפונקציות של תקשורת עם השרת: מחלקה של משתמשים ומחלקה של מוצרים. 
הפורט איתו אנו מתחברים לשרת הוא פורט 3000.
על מנת להריץ את הפונקציות נרשום את השורה הבאה עבור המשתמשים או המוצרים בהתאמה:
http://localhost:3000/items
http://localhost:3000/users
ובכדי לבדוק את הפונקציות השונות נוסיף \ ואת שם הפונקציה אחריה.
לדוגמה עבור הפונקציה Hot5Products נרשום: 
http://localhost:3000/items/Hot5Products

 וכמובן נשנה בפוסטמן GET/POST/PUT בהתאמה בהתאם לסוג הפונקציה.

עבור המוצרים הפונקציות שנבנו:
•	/AllProducts
פונקציה GET שמחזירה רשימה של כל המוצרים שקיימים בdata base.
•	/Hot5Products
פונקציה GET שמחזירה את כל המוצרים החמים מהשבוע.
•	/NewProducts
פונקציה GET שמחזירה את כל המוצרים החמים מהחודש האחרון.
•	/ProductsByCategory
פונקציה GET  , מקבלת מן המשתמש את הקטגוריה ומחזירה לו את כל המוצרים שנמצאים בקטגוריה שלפיה חיפש.
•	/SortProducts
פונקציה GET  , מקבלת מן המשתמש לפי מה למיין את המוצרים, הפונקציה ממיינת המוצרים לפי הערך שהכניס, ומחזירה לו את רשימת המוצרים ממוינים לפי סוג המיון שהכניס.  
•	/RecommendedProducts
פונקציה GET  , מקבלת מן המשתמש את הid שלו, ולפי קטגוריות המוצרים שהמשתמש אוהב, היא מחפשת לו מוצרים שמשתמשים אחרים הזמינו לפי אותם הקטגוריות שהוא אוהב, ולבסוף מחזירה לו את המוצרים המומלצים שכנראה יאהב לפי אותם הקטגוריות שהוא אוהב. 
•	/SearchProductsByName
פונקציה GET , מחפשת מוצרים לפי השם של המוצר שאותו הזין המשתמש.


•	/SearchProsuctsByColor
פונקציה GET , המשתמש מזין את הצבע של המוצר שברצונו למצוא, והשרת מחזיר לו את כל המוצרים באותו הצבע שקיימים בdata base. 
•	/SearchProductsBySize
פונקציה GET , המשתמש מזין את המידה של המוצר שברצונו למצוא, והשרת מחזיר לו את כל המוצרים באותו הצבע שקיימים בdata base. 
•	/IsProductAvailable
פונקציה GET, המשתמש מזין את הid של המוצר, והשרת בודק בdata base האם המוצר קיים במערכת, אם המוצר קיים הוא מחזיר לו אותו, אחרת הוא מחזיר שאינו קיים.
•	/DeleteProduct
פונקציה POST, הadmin מכניס id של מוצר שברצונו למחוק מן הdata base והשרת מוצא את המוצר לפי הid ומוחק אותו מן הdata base.
•	/AddProduct
פונקציה POST , הadmin מזין פרטים אודות המוצר החדש שברצונו להוסיף לdatabase.
הוא מזין את הפרטים הבאים: קוד, שם, מידה, צבע, כמות, מחיר, קטגוריה, יום, חודש, ושנה.
במידה והמוצר נוסף בהצלחה לdata base , נשלחת הודעה כי ההוספה התבצעה בהצלחה אחרת נשלחת שגיאה.
•	/UpdateStock
 	פונקציית PUT , הadmin מזין את הid של המוצר ואת הכמות ממנו שברצונו לעדכן בdata	base. השרת מקבל את הפרטים הללו ומעדכן את הנתונים של המוצר בdata base. 
נשלחת הודעת תגובה לפעולה כי העדכון נוצר בהצלחה אם הפעולה הצליחה ואם לא נשלחת הודעת שגיאה.

עבור המשתמשים הפונקציות שבנינו:
•	/Login
פונקציית GET , המשתמש מזין שם משתמש וסיסמה והשרת בודק האם המשתמש קיים במערכת. במידה וכן הוא מחזיר לו true אחרת הוא מחזיר לו false.
•	/Registration
פונקציית POST, המשתמש מזין את הפרטים הבאים: שם משתמש, סיסמה, שם פרטי, שם משפחה, מין, אימייל, טלפון, תאריך לידה, כתובת, ארץ, תשובה לשאלה, והאם הוא מעוניין בקטגוריות חולצות, מכנסים, שמלות, חצאיות ותחתונים.
השרת קולט את הפרטים הבאים ומכניס אותם לdatabase , במידה וההכנסה התבצעה בהצלחה הוא שולח הודעת true  אחרת רושם false.
•	/ForgetPassword
פונקציית POST, במידה והמשתמש שכח את הסיסמה שלו, הוא מזין את שם המשתמש ואת התשובה לשאלה הסודית. המערכת בודקת בdatabase האם המשתמש קיים והאם התשובה היא נכונה בהתאם לקלט שהזין בעת ההרשמה. במידה וכן הוא מחזיר למשתמש את הסיסמה שלו. אחרת רושם הודעת שגיאה.
•	/ShowPastOrders
פונקצית GET , המשתמש מזין את הקוד משתמש שלו ומקבל רשימת כל ההזמנות שבוצעו בעבר.

•	/AddOrder
פונקציית POST , המשתמש מבצע הזמנה, הוא מזין את הפרטים הבאים: שם משתמש, שמו, תאריך הזמנה, תאריך שליחת הזמנה ואת המטבע. השרת מקבל את הפרטים שהמשתמש הזין ומכניס אותם לdatabase ויוצר בעצם הזמנה חדשה.
•	/ListUsers
פונקציית GET , השרת מחזיר רשימה של כל המשתמשים שקיימים בdatabase.
•	/addUser
פונקציית POST, הadmin מוסיף משתמש חדש. הוא מזין את הפרטים הבאים על מנת ליצור משתמש חדש: שם משתמש, סיסמה, שם פרטי, שם משפחה, מין, אימייל, טלפון, תאריך לידה, כתובת, ארץ, תשובה לשאלה, והאם הוא מעוניין בקטגוריות חולצות, מכנסים, שמלות, חצאיות ותחתונים. השרת קולט את הפרטים הבאים ומכניס אותם לdatabase , במידה וההכנסה התבצעה בהצלחה הוא שולח הודעת true  אחרת רושם false.
•	/DeleteUser
פונקציית DELETE  , הadmin מקבל את הid של המשתמש שברצונו למחוק, והשרת מחפש את המשתמש הזה בdatabase ומוחק אותו ממנו. כשהפעולה הצליחה הוא מחזיר success  אחרת מחזיר fail.
securityAnswer	country	address	birthDay	phone	email	gender	lastName	firstName	password	userName	
David	israel	Rager 111	5/5/1991	0509999999	tal@gmail.com	female	Rosentzeig	Tal	12345678	tal	user
polak	Israel	Rager 2	2/5/1991	0509999999	p@gmail.com	Female	P	Merav	12345678	merav	user
Mic	Israel	Rager 190	1/1/1992	0509911922	mic@gmail.com	Female	Fe	Michal	12345678	michal	user
Page	Israel	Rager 19	1/1/1992	0509911922	m@gmail.com
Female	Fe	Mor	12345678	Mor	user
moran	Israel	RAGER 113	9/2/1991	0509911999	ma@gmail.com	Female	Az	Morna	12345678	Moran	user
david	Israel	RAGER 111	3/7/1994	0509999999	noa@gmail.com
Female	Tz	Noa	12345678	Noa	user
noamg	Israel	Rager 12	9/5/1993	0509111922	noam@gmail.com	Female	G	Noam	12345678	noam	user
rotem	Israel	Rager 21	2/6/1992	0509999999	rc@gmail.com	Female	C	Rotem	12345678	rotem	user
Meromim	Israel	Rager 10	3/6/1991	0509999999	shaked@gmail.com	male	Hazon	Shaked	12345678	shaked	user 
Dorot	Israel	Rager 190	5/5/1991	0509911999	sf@gmail.com	Female	Fe	Stephanie	12345678	steph	user
Nitzanim	Israel	Rager 23	5/10/1993	0509999999	dana@gmail.com	Female	Feldman	Dana	12345678	dana	admin
Herzel	israel	Rager 7	27/5/1992	0509999999	yarden@gmail.com	Female	page	yarden	12345678	yarden	admin
•	/AddToCart
פונקציית POST , המשתמש מוסיף לעגלה מוצרים שברצונו להזמין. המשתמש מזין שם משתמש, את המוצר ואת המחיר של המוצר.
•	/RemoveFromCart
פונקציית POST , המשתמש מסיר מן העגלה מוצרים. המשתמש מזין שם משתמש, את קוד המוצר. השרת מסיר את מוצר מן העגלה, במידה והפעולה הצליחה מחזיר success  אחרת מחזיר fail.
•	/LastEntry
פונקציית GET , מעודכן למשתמש את הזמן האחרון בו הוא נכנס למערכת. תאריך ושעה.


