<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مكتب أسرع للخدمات الطلابية - نظام المحاسبة</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f7f6;
            color: #333;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-height: 100vh;
            margin: 0;
        }
        .container {
            max-width: 900px;
            width: 100%;
            margin: 2rem auto;
            padding: 1.5rem;
            background-color: #ffffff;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            flex-grow: 1;
        }
        input[type="number"], input[type="date"], input[type="text"], input[type="email"], input[type="password"], input[type="tel"], textarea, select {
            border: 1px solid #ccc;
            border-radius: 4px;
            padding: 0.75rem 1rem;
            width: 100%;
            transition: border-color 0.2s;
            background-color: white;
        }
        input[type="number"]:focus, input[type="date"]:focus, input[type="text"]:focus, input[type="email"]:focus, input[type="password"]:focus, input[type="tel"]:focus, textarea:focus, select:focus {
            outline: none;
            border-color: #4CAF50;
        }
        button {
            background-color: #4CAF50;
            color: white;
            padding: 0.75rem 1.5rem;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.2s;
            font-weight: bold;
        }
        button:hover {
            background-color: #45a049;
        }
        .nav-button {
            background-color: #6c757d;
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.2s;
            font-weight: bold;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            white-space: nowrap;
        }
        .nav-button:hover {
            background-color: #5a6268;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1.5rem;
        }
        th, td {
            border: 1px solid #eee;
            padding: 0.75rem 1rem;
            text-align: right;
        }
        th {
            background-color: #e0e0e0;
            font-weight: bold;
        }
        .summary-box {
            background-color: #f9f9f9;
            border: 1px solid #eee;
            border-radius: 6px;
            padding: 1rem;
            margin-bottom: 1.5rem;
        }
        .text-green-600 { color: #28a745; }
        .text-red-600 { color: #dc3545; }
        .text-blue-600 { color: #007bff; }
        .user-list-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0.5rem 0;
            border-bottom: 1px dashed #eee;
        }
        .user-list-item:last-child {
            border-bottom: none;
        }
        #login-form-container {
            max-width: 400px;
            width: 100%;
            padding: 2rem;
            background-color: #ffffff;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        .hidden {
            display: none;
        }
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 1rem;
            margin-top: 2rem;
            width: 100%;
        }
        footer a {
            color: #4CAF50;
            text-decoration: none;
            font-weight: bold;
        }
        footer a:hover {
            text-decoration: underline;
        }
        .loading-indicator {
            display: inline-block;
            width: 1rem;
            height: 1rem;
            border: 2px solid rgba(255,255,255,.3);
            border-radius: 50%;
            border-top-color: #fff;
            animation: spin 1s ease-in-out infinite;
            -webkit-animation: spin 1s ease-in-out infinite;
            margin-right: 0.5rem;
        }
        @keyframes spin {
            to { -webkit-transform: rotate(360deg); }
        }
        @-webkit-keyframes spin {
            to { -webkit-transform: rotate(360deg); }
        }
        .excluded-from-total {
            background-color: #fff3cd;
            font-style: italic;
            color: #856404;
        }
        .editable-title {
            display: inline-block;
            cursor: pointer;
            border-bottom: 1px dashed #ccc;
        }
        .editable-title:hover {
            border-bottom-color: #4CAF50;
        }
    </style>
</head>
<body>
    <div id="login-form-container" class="hidden">
        <h2 class="text-2xl font-bold mb-6 text-gray-800">تسجيل الدخول</h2>
        <div class="mb-4">
            <label for="loginEmail" class="block text-gray-700 text-sm font-bold mb-2 text-right">البريد الإلكتروني:</label>
            <input type="email" id="loginEmail" placeholder="أدخل بريدك الإلكتروني" class="shadow-sm block w-full sm:text-sm border-gray-300 rounded-md">
        </div>
        <div class="mb-6">
            <label for="loginPassword" class="block text-gray-700 text-sm font-bold mb-2 text-right">كلمة المرور:</label>
            <input type="password" id="loginPassword" placeholder="أدخل كلمة المرور" class="shadow-sm block w-full sm:text-sm border-gray-300 rounded-md">
        </div>
        <button id="loginBtn" class="w-full mb-4">تسجيل الدخول</button>
        <p class="text-sm text-gray-600 mt-2">
            <a href="#" class="text-blue-600 hover:underline">هل نسيت كلمة السر؟</a>
        </p>
    </div>

    <div id="app-container" class="container hidden">
        <div class="flex justify-between items-center mb-6">
            <h1 class="text-3xl font-bold text-gray-800"><span class="text-blue-600">مكتب أسرع</span> للخدمات الطلابية</h1>
            <button id="logoutBtn" class="bg-gray-500 hover:bg-gray-700 text-white py-2 px-4 rounded text-sm">تسجيل الخروج</button>
        </div>
        <p class="text-xl text-center text-gray-600 mb-8">نظام محاسبي لعمليات الكاش والشبكة</p>

        <div class="flex flex-wrap justify-center gap-3 mb-8">
            <button class="nav-button" data-section="addTransactionSection">إضافة معاملة</button>
            <button class="nav-button" data-section="addSpecialNetworkSection">إضافة عملية شبكة خاصة</button>
            <button class="nav-button" data-section="transactionsLogSection">سجل المعاملات</button>
            <button class="nav-button" data-section="excelReportSection">تقرير العمليات</button>
            <button class="nav-button" data-section="networkReportSection">تقرير الشبكة</button>
            <button class="nav-button" data-section="dailyIncomeSection">الدخل اليومي</button>
            <button class="nav-button" data-section="otherOperationsSection">عمليات أخرى</button>
            <button class="nav-button" data-section="changePasswordSection">تغيير كلمة السر</button>
            <button class="nav-button" data-section="adminSection" id="adminNavButton">إدارة المستخدمين</button>
        </div>

        <div class="summary-box mb-8">
            <h2 class="text-xl font-semibold mb-3">المستخدم الحالي: <span id="currentUserName" class="text-blue-600"></span> (<span id="currentUserRole" class="text-blue-600"></span>)</h2>
        </div>

        <div id="adminSection" class="summary-box mb-8 hidden">
            <h2 class="text-xl font-semibold mb-3">إدارة المستخدمين</h2>
            <div class="flex flex-col md:flex-row gap-4 mb-4">
                <input type="text" id="newUserName" placeholder="اسم المستخدم الجديد" class="flex-grow shadow-sm text-sm border-gray-300 rounded-md">
                <input type="email" id="newUserEmail" placeholder="البريد الإلكتروني" class="flex-grow shadow-sm text-sm border-gray-300 rounded-md">
                <input type="password" id="newUserPassword" placeholder="كلمة المرور" class="flex-grow shadow-sm text-sm border-gray-300 rounded-md">
                <input type="tel" id="newUserMobile" placeholder="رقم الجوال (اختياري)" class="flex-grow shadow-sm text-sm border-gray-300 rounded-md">
                <select id="newUserRole" class="shadow-sm text-sm border-gray-300 rounded-md w-full md:w-auto">
                    <option value="user">مستخدم عادي</option>
                    <option value="admin">مدير نظام</option>
                </select>
                <button id="addOrUpdateUserBtn" class="w-full md:w-auto">إضافة مستخدم</button>
            </div>
            <div id="userList" class="max-h-48 overflow-y-auto border border-gray-200 rounded-md p-2">
                <p class="text-center text-gray-500" id="noUsersMessage">لا يوجد مستخدمون مضافون بعد.</p>
            </div>
        </div>

        <div id="changePasswordSection" class="summary-box mb-8 hidden">
            <h2 class="text-xl font-semibold mb-3">تغيير كلمة المرور</h2>
            <p class="text-sm text-red-600 mb-4">
                تنبيه أمني: تغيير كلمة المرور هنا يتم على جهازك فقط ولا يتضمن تحققًا خارجياً (مثل رسائل SMS حقيقية).
                هذا النظام غير آمن للبيانات الحساسة.
            </p>
            <div class="mb-4">
                <label for="currentPassword" class="block text-gray-700 text-sm font-bold mb-2 text-right">كلمة المرور الحالية:</label>
                <input type="password" id="currentPassword" class="shadow-sm block w-full sm:text-sm border-gray-300 rounded-md">
            </div>
            <div class="mb-4">
                <label for="newPassword" class="block text-gray-700 text-sm font-bold mb-2 text-right">كلمة المرور الجديدة:</label>
                <input type="password" id="newPassword" class="shadow-sm block w-full sm:text-sm border-gray-300 rounded-md">
            </div>
            <div class="mb-4">
                <label for="confirmNewPassword" class="block text-gray-700 text-sm font-bold mb-2 text-right">تأكيد كلمة المرور الجديدة:</label>
                <input type="password" id="confirmNewPassword" class="shadow-sm block w-full sm:text-sm border-gray-300 rounded-md">
            </div>
            <div class="mb-6">
                <label for="mobileForVerification" class="block text-gray-700 text-sm font-bold mb-2 text-right">رقم الجوال المسجل (للتحقق):</label>
                <input type="tel" id="mobileForVerification" placeholder="أدخل رقم الجوال المسجل" class="shadow-sm block w-full sm:text-sm border-gray-300 rounded-md">
            </div>
            <button id="changePasswordBtn" class="w-full">تغيير كلمة المرور</button>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
            <div class="summary-box">
                <h2 class="text-xl font-semibold mb-3">ملخص اليومية (<span id="todayDate"></span>)</h2>
                <p class="text-lg mb-2">إجمالي دخل الكاش اليوم: <span id="todayCash" class="font-bold text-green-600">0</span> ريال</p>
                <p class="text-lg mb-2">إجمالي دخل الشبكة اليوم: <span id="todayNetwork" class="font-bold text-green-600">0</span> ريال</p>
                <p class="text-lg mb-2">إجمالي مصروفات اليوم: <span id="todayExpenses" class="font-bold text-red-600">0</span> ريال</p>
                <hr class="my-3">
                <p class="text-xl mb-2">صافي دخل اليوم: <span id="todayNet" class="font-bold text-blue-600">0</span> ريال</p>
                <p class="text-xl mb-2">نصيب المحل اليوم (50%): <span id="todayShopShare" class="font-bold text-blue-600">0</span> ريال</p>
                <p class="text-xl">نصيب العامل اليوم (50%): <span id="todayWorkerShare" class="font-bold text-blue-600">0</span> ريال</p>
            </div>

            <div class="summary-box">
                <h2 class="text-xl font-semibold mb-3">ملخص إجمالي المعاملات</h2>
                <div class="mb-4">
                    <label for="filterByUser" class="block text-gray-700 text-sm font-bold mb-2">تصفية حسب المستخدم:</label>
                    <select id="filterByUser" class="shadow-sm block w-full sm:text-sm border-gray-300 rounded-md">
                        <option value="all">جميع المستخدمين</option>
                    </select>
                </div>
                <p class="text-lg mb-2">إجمالي دخل الكاش: <span id="totalCash" class="font-bold text-green-600">0</span> ريال</p>
                <p class="text-lg mb-2">إجمالي دخل الشبكة: <span id="totalNetwork" class="font-bold text-green-600">0</span> ريال</p>
                <p class="text-lg mb-2">إجمالي المصروفات: <span id="totalExpenses" class="font-bold text-red-600">0</span> ريال</p>
                <hr class="my-3">
                <p class="text-xl mb-2">صافي الدخل الكلي: <span id="totalNet" class="font-bold text-blue-600">0</span> ريال</p>
                <p class="text-xl mb-2">نصيب المحل الكلي (50%): <span id="shopShare" class="font-bold text-blue-600">0</span> ريال</p>
                <p class="text-xl">نصيب العامل الكلي (50%): <span id="workerShare" class="font-bold text-blue-600">0</span> ريال</p>
                <button id="getFinancialInsightBtn" class="bg-blue-500 hover:bg-blue-600 text-white py-2 px-4 rounded mt-4 text-sm w-full">
                    ✨ رؤى مالية (للمدير)
                    <span id="financialInsightLoading" class="loading-indicator hidden"></span>
                </button>
                <div id="financialInsightOutput" class="mt-4 p-3 bg-blue-50 border border-blue-200 rounded text-sm text-gray-700 hidden"></div>
            </div>
        </div>

        <div id="dailyIncomeSection" class="summary-box mb-8 hidden">
            <h2 class="text-xl font-semibold mb-3">الدخل اليومي التفصيلي (<span id="dailyDetailDate"></span>)</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                <div class="flex flex-col">
                    <button id="calculateDailyCashBtn" class="bg-indigo-500 hover:bg-indigo-600 text-white py-2 px-4 rounded text-sm mb-2">
                        حساب الكاش لليوم
                    </button>
                    <p class="text-lg">إجمالي الكاش اليومي: <span id="dailyDetailCash" class="font-bold text-green-600">0</span> ريال</p>
                </div>
                <div class="flex flex-col">
                    <button id="calculateDailyNetworkBtn" class="bg-teal-500 hover:bg-teal-600 text-white py-2 px-4 rounded text-sm mb-2">
                        حساب الشبكة لليوم
                    </button>
                    <p class="text-lg">إجمالي الشبكة اليومي: <span id="dailyDetailNetwork" class="font-bold text-green-600">0</span> ريال</p>
                </div>
            </div>
            <hr class="my-4">
            <p class="text-xl mb-2">إجمالي الدخل اليومي (كاش + شبكة): <span id="dailyDetailTotalIncome" class="font-bold text-blue-600">0</span> ريال</p>
            <p class="text-xl">نصيب الدخل اليومي مقسوم 2: <span id="dailyDetailHalfIncome" class="font-bold text-blue-600">0</span> ريال</p>
        </div>


        <div id="addTransactionSection" class="summary-box mb-8 hidden">
            <h2 class="text-xl font-semibold mb-3">إضافة معاملة جديدة</h2>
            <div class="mb-4">
                <label for="responsibleUser" class="block text-gray-700 text-sm font-bold mb-2">المستخدم المسؤول:</label>
                <select id="responsibleUser" class="shadow-sm focus:ring-green-500 focus:border-green-500 block w-full sm:text-sm border-gray-300 rounded-md">
                    <option value="">-- اختر مستخدم --</option>
                </select>
            </div>
            <div class="mb-4">
                <label for="transactionDate" class="block text-gray-700 text-sm font-bold mb-2">التاريخ:</label>
                <input type="date" id="transactionDate" class="shadow-sm focus:ring-green-500 focus:border-green-500 block w-full sm:text-sm border-gray-300 rounded-md">
            </div>
            <div class="mb-4">
                <label for="cashAmount" class="block text-gray-700 text-sm font-bold mb-2">مبلغ الكاش (الدخل):</label>
                <input type="number" id="cashAmount" placeholder="أدخل مبلغ الكاش" class="shadow-sm focus:ring-green-500 focus:border-green-500 block w-full sm:text-sm border-gray-300 rounded-md">
            </div>
            <div class="mb-4">
                <label for="networkAmount" class="block text-gray-700 text-sm font-bold mb-2">مبلغ الشبكة (الدخل):</label>
                <input type="number" id="networkAmount" placeholder="أدخل مبلغ الشبكة" class="shadow-sm focus:ring-green-500 focus:border-green-500 block w-full sm:text-sm border-gray-300 rounded-md">
                <div class="mt-2 flex items-center">
                    <input type="checkbox" id="excludeFromTotalCheckbox" class="ml-2 w-auto">
                    <label for="excludeFromTotalCheckbox" class="text-gray-700 text-sm">لا تحتسب في الإجمالي العام (خاص بالشبكة)</label>
                </div>
            </div>
            <div class="mb-4">
                <label for="expenseAmount" class="block text-gray-700 text-sm font-bold mb-2">مبلغ المصروف (المصروفات):</label>
                <input type="number" id="expenseAmount" placeholder="أدخل مبلغ المصروف" class="shadow-sm focus:ring-green-500 focus:border-green-500 block w-full sm:text-sm border-gray-300 rounded-md">
            </div>
            <div class="mb-6">
                <label for="description" class="block text-gray-700 text-sm font-bold mb-2">الوصف (اختياري):</label>
                <textarea id="description" placeholder="وصف المعاملة" rows="2" class="shadow-sm focus:ring-green-500 focus:border-green-500 block w-full sm:text-sm border-gray-300 rounded-md"></textarea>
                <button id="enhanceDescriptionBtn" class="bg-purple-500 hover:bg-purple-600 text-white py-2 px-4 rounded mt-2 text-sm w-full">
                    ✨ تحسين الوصف
                    <span id="descriptionLoading" class="loading-indicator hidden"></span>
                </button>
            </div>
            <button id="addTransactionBtn" class="w-full">إضافة معاملة</button>
        </div>

        <div id="addSpecialNetworkSection" class="summary-box mb-8 hidden">
            <h2 class="text-xl font-semibold mb-3">إضافة عملية شبكة خاصة</h2>
            <p class="text-sm text-gray-600 mb-4">
                هذه العمليات تظهر فقط في "تقرير الشبكة" ولا تحتسب في إجمالي الدخل العام.
            </p>
            <div class="mb-4">
                <label for="specialNetworkUser" class="block text-gray-700 text-sm font-bold mb-2">المستخدم المسؤول:</label>
                <select id="specialNetworkUser" class="shadow-sm focus:ring-green-500 focus:border-green-500 block w-full sm:text-sm border-gray-300 rounded-md">
                    <option value="">-- اختر مستخدم --</option>
                </select>
            </div>
            <div class="mb-4">
                <label for="specialNetworkDate" class="block text-gray-700 text-sm font-bold mb-2">التاريخ:</label>
                <input type="date" id="specialNetworkDate" class="shadow-sm focus:ring-green-500 focus:border-green-500 block w-full sm:text-sm border-gray-300 rounded-md">
            </div>
            <div class="mb-4">
                <label for="specialNetworkAmount" class="block text-gray-700 text-sm font-bold mb-2">مبلغ الشبكة:</label>
                <input type="number" id="specialNetworkAmount" placeholder="أدخل مبلغ الشبكة" class="shadow-sm focus:ring-green-500 focus:border-green-500 block w-full sm:text-sm border-gray-300 rounded-md">
            </div>
            <div class="mb-6">
                <label for="specialNetworkDescription" class="block text-gray-700 text-sm font-bold mb-2">الوصف (اختياري):</label>
                <textarea id="specialNetworkDescription" placeholder="وصف عملية الشبكة الخاصة" rows="2" class="shadow-sm focus:ring-green-500 focus:border-green-500 block w-full sm:text-sm border-gray-300 rounded-md"></textarea>
            </div>
            <button id="addSpecialNetworkBtn" class="w-full">إضافة عملية شبكة خاصة</button>
        </div>


        <h2 class="text-2xl font-bold mb-4 text-gray-800">سجل المعاملات</h2>
        <div id="transactionsLogSection" class="overflow-x-auto summary-box mb-8 hidden">
            <table class="min-w-full">
                <thead>
                    <tr>
                        <th>الرقم</th>
                        <th>رقم العملية</th>
                        <th>التاريخ</th>
                        <th>المستخدم</th>
                        <th>الكاش (ريال)</th>
                        <th>الشبكة (ريال)</th>
                        <th>المصروف (ريال)</th>
                        <th>الإجمالي (ريال)</th>
                        <th>الوصف</th>
                        <th>إجراءات</th>
                    </tr>
                </thead>
                <tbody id="transactionsTableBody">
                </tbody>
            </table>
        </div>

        <h2 class="text-2xl font-bold mb-4 text-gray-800 mt-8">تقرير العمليات (شكل Excel)</h2>
        <div id="excelReportSection" class="overflow-x-auto summary-box mb-8 hidden">
            <table class="min-w-full">
                <thead>
                    <tr>
                        <th>الرقم</th>
                        <th>رقم العملية</th>
                        <th>التاريخ</th>
                        <th>اليوم</th>
                        <th>المستخدم</th>
                        <th>مبلغ العملية (صافي)</th>
                        <th>الوصف</th>
                    </tr>
                </thead>
                <tbody id="excelReportTableBody">
                </tbody>
            </table>
        </div>

        <h2 class="text-2xl font-bold mb-4 text-gray-800 mt-8">تقرير عمليات الشبكة (شكل Excel)</h2>
        <div id="networkReportSection" class="overflow-x-auto summary-box mb-8 hidden">
            <table class="min-w-full">
                <thead>
                    <tr>
                        <th>الرقم</th>
                        <th>رقم العملية</th>
                        <th>التاريخ</th>
                        <th>اليوم</th>
                        <th>المستخدم</th>
                        <th>مبلغ الشبكة (ريال)</th>
                        <th>الوصف</th>
                    </tr>
                </thead>
                <tbody id="networkReportTableBody">
                </tbody>
            </table>
        </div>

        <div id="otherOperationsSection" class="summary-box mb-8 hidden">
            <h2 class="text-xl font-semibold mb-3">
                <span id="otherOperationsTitleDisplay" class="editable-title">عمليات أخرى</span>
                <input type="text" id="otherOperationsTitleInput" class="hidden inline-block w-64 text-base px-2 py-1 border rounded" placeholder="تعديل اسم القسم">
                <button id="saveOtherOperationsTitleBtn" class="hidden bg-blue-500 hover:bg-blue-600 text-white py-1 px-3 rounded text-sm mr-2">حفظ</button>
            </h2>
            
            <div class="mb-6">
                <label for="otherOperationsNotes" class="block text-gray-700 text-sm font-bold mb-2">ملاحظات عامة:</label>
                <textarea id="otherOperationsNotes" placeholder="أدخل ملاحظاتك هنا..." rows="4" class="shadow-sm focus:ring-green-500 focus:border-green-500 block w-full sm:text-sm border-gray-300 rounded-md"></textarea>
            </div>

            <h3 class="text-lg font-semibold mb-3">إضافة عملية أخرى جديدة</h3>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-4">
                <div>
                    <label for="otherOperationName" class="block text-gray-700 text-sm font-bold mb-2">اسم العملية:</label>
                    <input type="text" id="otherOperationName" placeholder="مثال: زيارة عميل، صيانة" class="shadow-sm text-sm border-gray-300 rounded-md">
                </div>
                <div>
                    <label for="otherOperationNumber" class="block text-gray-700 text-sm font-bold mb-2">رقم العملية:</label>
                    <input type="text" id="otherOperationNumber" placeholder="رقم مرجعي" class="shadow-sm text-sm border-gray-300 rounded-md">
                </div>
                <div>
                    <label for="otherOperationDate" class="block text-gray-700 text-sm font-bold mb-2">التاريخ:</label>
                    <input type="date" id="otherOperationDate" class="shadow-sm text-sm border-gray-300 rounded-md">
                </div>
                <div>
                    <label for="otherOperationDescription" class="block text-gray-700 text-sm font-bold mb-2">الوصف (اختياري):</label>
                    <textarea id="otherOperationDescription" placeholder="تفاصيل العملية" rows="1" class="shadow-sm text-sm border-gray-300 rounded-md"></textarea>
                </div>
            </div>
            <button id="addOtherOperationBtn" class="w-full">إضافة عملية أخرى</button>

            <h3 class="text-lg font-semibold mb-3 mt-6">سجل العمليات الأخرى</h3>
            <div class="overflow-x-auto">
                <table class="min-w-full">
                    <thead>
                        <tr>
                            <th>الرقم</th>
                            <th>اسم العملية</th>
                            <th>رقم العملية</th>
                            <th>التاريخ</th>
                            <th>اليوم</th>
                            <th>الوصف</th>
                            <th>إجراءات</th>
                        </tr>
                    </thead>
                    <tbody id="otherOperationsTableBody">
                    </tbody>
                </table>
            </div>
        </div>


    </div>

    <footer>
        <p>&copy; 2025 مكتب أسرع للخدمات الطلابية. جميع الحقوق محفوظة.</p>
        <p class="mt-2">
            <button id="copyAppLinkBtn" class="bg-blue-600 hover:bg-blue-700 text-white py-1 px-3 rounded text-sm">نسخ رابط التطبيق</button>
        </p>
    </footer>

    <script>
        const loginFormContainer = document.getElementById('login-form-container');
        const appContainer = document.getElementById('app-container');
        const loginEmailInput = document.getElementById('loginEmail');
        const loginPasswordInput = document.getElementById('loginPassword');
        const loginBtn = document.getElementById('loginBtn');
        const logoutBtn = document.getElementById('logoutBtn');

        const currentUserNameSpan = document.getElementById('currentUserName');
        const currentUserRoleSpan = document.getElementById('currentUserRole');

        const transactionDateInput = document.getElementById('transactionDate');
        const cashAmountInput = document.getElementById('cashAmount');
        const networkAmountInput = document.getElementById('networkAmount');
        const excludeFromTotalCheckbox = document.getElementById('excludeFromTotalCheckbox');
        const expenseAmountInput = document.getElementById('expenseAmount');
        const descriptionInput = document.getElementById('description');
        const responsibleUserSelect = document.getElementById('responsibleUser');
        const addTransactionBtn = document.getElementById('addTransactionBtn');
        const transactionsTableBody = document.getElementById('transactionsTableBody');
        const excelReportTableBody = document.getElementById('excelReportTableBody');
        const networkReportTableBody = document.getElementById('networkReportTableBody');

        const totalCashSpan = document.getElementById('totalCash');
        const totalNetworkSpan = document.getElementById('totalNetwork');
        const totalExpensesSpan = document.getElementById('totalExpenses');
        const totalNetSpan = document.getElementById('totalNet');
        const shopShareSpan = document.getElementById('shopShare');
        const workerShareSpan = document.getElementById('workerShare');

        const todayDateSpan = document.getElementById('todayDate');
        const todayCashSpan = document.getElementById('todayCash');
        const todayNetworkSpan = document.getElementById('todayNetwork');
        const todayExpensesSpan = document.getElementById('todayExpenses');
        const todayNetSpan = document.getElementById('todayNet');
        const todayShopShareSpan = document.getElementById('todayShopShare');
        const todayWorkerShareSpan = document.getElementById('todayWorkerShare');

        const dailyIncomeSection = document.getElementById('dailyIncomeSection');
        const dailyDetailDateSpan = document.getElementById('dailyDetailDate');
        const calculateDailyCashBtn = document.getElementById('calculateDailyCashBtn');
        const dailyDetailCashSpan = document.getElementById('dailyDetailCash');
        const calculateDailyNetworkBtn = document.getElementById('calculateDailyNetworkBtn');
        const dailyDetailNetworkSpan = document.getElementById('dailyDetailNetwork');
        const dailyDetailTotalIncomeSpan = document.getElementById('dailyDetailTotalIncome');
        const dailyDetailHalfIncomeSpan = document.getElementById('dailyDetailHalfIncome');

        const adminSection = document.getElementById('adminSection');
        const newUserNameInput = document.getElementById('newUserName');
        const newUserEmailInput = document = document.getElementById('newUserEmail');
        const newUserPasswordInput = document.getElementById('newUserPassword');
        const newUserMobileInput = document.getElementById('newUserMobile');
        const newUserRoleSelect = document.getElementById('newUserRole');
        const addOrUpdateUserBtn = document.getElementById('addOrUpdateUserBtn');
        const userListDiv = document.getElementById('userList');
        const noUsersMessage = document.getElementById('noUsersMessage');
        const filterByUserSelect = document.getElementById('filterByUser');

        const currentPasswordInput = document.getElementById('currentPassword');
        const newPasswordInput = document.getElementById('newPassword');
        const confirmNewPasswordInput = document.getElementById('confirmNewPassword');
        const mobileForVerificationInput = document.getElementById('mobileForVerification');
        const changePasswordBtn = document.getElementById('changePasswordBtn');

        const enhanceDescriptionBtn = document.getElementById('enhanceDescriptionBtn');
        const descriptionLoading = document.getElementById('descriptionLoading');
        const getFinancialInsightBtn = document.getElementById('getFinancialInsightBtn');
        const financialInsightLoading = document.getElementById('financialInsightLoading');
        const financialInsightOutput = document.getElementById('financialInsightOutput');

        const copyAppLinkBtn = document.getElementById('copyAppLinkBtn');

        const addTransactionSection = document.getElementById('addTransactionSection');
        const transactionsLogSection = document.getElementById('transactionsLogSection');
        const excelReportSection = document.getElementById('excelReportSection');
        const networkReportSection = document.getElementById('networkReportSection');
        const changePasswordSection = document.getElementById('changePasswordSection');
        const adminNavButton = document.getElementById('adminNavButton');
        
        const addSpecialNetworkSection = document.getElementById('addSpecialNetworkSection');
        const specialNetworkUserSelect = document.getElementById('specialNetworkUser');
        const specialNetworkDateInput = document.getElementById('specialNetworkDate');
        const specialNetworkAmountInput = document.getElementById('specialNetworkAmount');
        const specialNetworkDescriptionInput = document.getElementById('specialNetworkDescription');
        const addSpecialNetworkBtn = document.getElementById('addSpecialNetworkBtn');

        // Other Operations Section Elements
        const otherOperationsSection = document.getElementById('otherOperationsSection');
        const otherOperationsTitleDisplay = document.getElementById('otherOperationsTitleDisplay');
        const otherOperationsTitleInput = document.getElementById('otherOperationsTitleInput');
        const saveOtherOperationsTitleBtn = document.getElementById('saveOtherOperationsTitleBtn');
        const otherOperationsNotesTextarea = document.getElementById('otherOperationsNotes');
        const otherOperationNameInput = document.getElementById('otherOperationName');
        const otherOperationNumberInput = document.getElementById('otherOperationNumber');
        const otherOperationDateInput = document.getElementById('otherOperationDate');
        const otherOperationDescriptionInput = document.getElementById('otherOperationDescription');
        const addOtherOperationBtn = document.getElementById('addOtherOperationBtn');
        const otherOperationsTableBody = document.getElementById('otherOperationsTableBody');


        let users = [];
        let transactions = [];
        let currentUser = null;
        let transactionCounter = 0;
        let otherOperations = []; // New array for other operations
        let otherOperationsNotes = ''; // New variable for notes
        let otherOperationsTitle = 'عمليات أخرى'; // New variable for customizable title
        let otherOperationCounter = 0; // New counter for other operations

        async function callGeminiAPI(prompt) {
            const apiKey = "";
            const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;
            
            let chatHistory = [];
            chatHistory.push({ role: "user", parts: [{ text: prompt }] });
            const payload = { contents: chatHistory };

            try {
                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });
                const result = await response.json();

                if (result.candidates && result.candidates.length > 0 &&
                    result.candidates[0].content && result.candidates[0].content.parts &&
                    result.candidates[0].content.parts.length > 0) {
                    return result.candidates[0].content.parts[0].text;
                } else {
                    console.error('Gemini API response structure unexpected:', result);
                    return 'تعذر الحصول على استجابة من الذكاء الاصطناعي.';
                }
            } catch (error) {
                console.error('Error calling Gemini API:', error);
                return 'حدث خطأ أثناء الاتصال بالذكاء الاصطناعي.';
            }
        }

        function saveToLocalStorage() {
            localStorage.setItem('accountingAppUsers', JSON.stringify(users));
            localStorage.setItem('accountingAppTransactions', JSON.stringify(transactions));
            localStorage.setItem('accountingAppTransactionCounter', transactionCounter.toString());
            localStorage.setItem('accountingAppOtherOperations', JSON.stringify(otherOperations)); // Save new data
            localStorage.setItem('accountingAppOtherOperationsNotes', otherOperationsNotes); // Save new notes
            localStorage.setItem('accountingAppOtherOperationsTitle', otherOperationsTitle); // Save new title
            localStorage.setItem('accountingAppOtherOperationCounter', otherOperationCounter.toString()); // Save new counter
        }

        function loadFromLocalStorage() {
            const storedUsers = localStorage.getItem('accountingAppUsers');
            const storedTransactions = localStorage.getItem('accountingAppTransactions');
            const storedCounter = localStorage.getItem('accountingAppTransactionCounter');
            const storedOtherOperations = localStorage.getItem('accountingAppOtherOperations'); // Load new data
            const storedOtherOperationsNotes = localStorage.getItem('accountingAppOtherOperationsNotes'); // Load new notes
            const storedOtherOperationsTitle = localStorage.getItem('accountingAppOtherOperationsTitle'); // Load new title
            const storedOtherOperationCounter = localStorage.getItem('accountingAppOtherOperationCounter'); // Load new counter

            if (storedUsers) {
                users = JSON.parse(storedUsers);
            }
            if (storedTransactions) {
                transactions = JSON.parse(storedTransactions);
            }
            if (storedCounter) {
                transactionCounter = parseInt(storedCounter, 10);
            }
            if (storedOtherOperations) { // Load new data
                otherOperations = JSON.parse(storedOtherOperations);
            }
            if (storedOtherOperationsNotes) { // Load new notes
                otherOperationsNotes = storedOtherOperationsNotes;
            }
            if (storedOtherOperationsTitle) { // Load new title
                otherOperationsTitle = storedOtherOperationsTitle;
            }
            if (storedOtherOperationCounter) { // Load new counter
                otherOperationCounter = parseInt(storedOtherOperationCounter, 10);
            }
        }

        function showLoginForm() {
            loginFormContainer.classList.remove('hidden');
            appContainer.classList.add('hidden');
        }

        function showApp() {
            loginFormContainer.classList.add('hidden');
            appContainer.classList.remove('hidden');
            updateUIForCurrentUser();
            renderUserList();
            renderTransactions();
            updateDailySummary();
            updateDailyDetailSummary();
            renderExcelReport();
            renderNetworkExcelReport();
            renderOtherOperationsTable(); // Render new table
            showSection('addTransactionSection');
            
            // Set initial values for Other Operations section
            otherOperationsNotesTextarea.value = otherOperationsNotes;
            otherOperationsTitleDisplay.textContent = otherOperationsTitle;
            otherOperationsTitleInput.value = otherOperationsTitle;
            otherOperationDateInput.value = todayFormatted; // Set date for other operations
        }

        function login() {
            const email = loginEmailInput.value;
            const password = loginPasswordInput.value;

            const user = users.find(u => u.email === email && u.password === password);

            if (user) {
                currentUser = user;
                sessionStorage.setItem('currentUser', JSON.stringify(currentUser));
                showApp();
            } else {
                alert('البريد الإلكتروني أو كلمة المرور غير صحيحة.');
            }
        }

        function logout() {
            currentUser = null;
            sessionStorage.removeItem('currentUser');
            showLoginForm();
            loginEmailInput.value = '';
            loginPasswordInput.value = '';
        }

        function checkLoginStatus() {
            const storedCurrentUser = sessionStorage.getItem('currentUser');
            if (storedCurrentUser) {
                currentUser = JSON.parse(storedCurrentUser);
                showApp();
            } else {
                showLoginForm();
            }
        }

        function updateUIForCurrentUser() {
            if (currentUser) {
                currentUserNameSpan.textContent = currentUser.name;
                currentUserRoleSpan.textContent = currentUser.role === 'admin' ? 'مدير نظام' : 'مستخدم عادي';

                if (currentUser.role === 'admin') {
                    adminSection.classList.remove('hidden');
                    adminNavButton.classList.remove('hidden');
                    getFinancialInsightBtn.classList.remove('hidden');
                } else {
                    adminSection.classList.add('hidden');
                    adminNavButton.classList.add('hidden');
                    getFinancialInsightBtn.classList.add('hidden');
                }
                
                populateUserSelects();
                if (currentUser.role === 'user') {
                    responsibleUserSelect.value = currentUser.name;
                    responsibleUserSelect.disabled = true;
                    specialNetworkUserSelect.value = currentUser.name;
                    specialNetworkUserSelect.disabled = true;
                } else {
                    responsibleUserSelect.disabled = false;
                    specialNetworkUserSelect.disabled = false;
                }
            }
        }

        function renderUserList() {
            userListDiv.innerHTML = '';
            if (users.length === 0) {
                userListDiv.appendChild(noUsersMessage);
                noUsersMessage.style.display = 'block';
            } else {
                noUsersMessage.style.display = 'none';
                users.forEach(user => {
                    const userItem = document.createElement('div');
                    userItem.className = 'user-list-item';
                    userItem.innerHTML = `
                        <span class="text-gray-800">${user.name} (${user.email}) - ${user.role === 'admin' ? 'مدير' : 'مستخدم'} ${user.mobile ? `(${user.mobile})` : ''}</span>
                        <button class="bg-red-500 hover:bg-red-700 text-white py-1 px-2 rounded text-sm" onclick="deleteUser('${user.email}')">حذف</button>
                    `;
                    userListDiv.appendChild(userItem);
                });
            }
            populateUserSelects();
            saveToLocalStorage();
        }

        function populateUserSelects() {
            responsibleUserSelect.innerHTML = '<option value="">-- اختر مستخدم --</option>';
            specialNetworkUserSelect.innerHTML = '<option value="">-- اختر مستخدم --</option>';
            filterByUserSelect.innerHTML = '<option value="all">جميع المستخدمين</option>';

            users.forEach(user => {
                const option1 = document.createElement('option');
                option1.value = user.name;
                option1.textContent = user.name;
                responsibleUserSelect.appendChild(option1);

                const option2 = document.createElement('option');
                option2.value = user.name;
                option2.textContent = user.name;
                filterByUserSelect.appendChild(option2);

                const option3 = document.createElement('option');
                option3.value = user.name;
                option3.textContent = user.name;
                specialNetworkUserSelect.appendChild(option3);
            });

            if (currentUser) {
                if (currentUser.role === 'user') {
                    responsibleUserSelect.value = currentUser.name;
                    responsibleUserSelect.disabled = true;
                    specialNetworkUserSelect.value = currentUser.name;
                    specialNetworkUserSelect.disabled = true;
                } else {
                    responsibleUserSelect.disabled = false;
                    specialNetworkUserSelect.disabled = false;
                }
            }
        }

        addOrUpdateUserBtn.addEventListener('click', () => {
            const userName = newUserNameInput.value.trim();
            const userEmail = newUserEmailInput.value.trim();
            const userPassword = newUserPasswordInput.value.trim();
            const userMobile = newUserMobileInput.value.trim();
            const userRole = newUserRoleSelect.value;

            if (!userName || !userEmail || !userPassword) {
                alert('الرجاء إدخال جميع بيانات المستخدم (الاسم، البريد الإلكتروني، كلمة المرور).');
                return;
            }

            if (!userEmail.includes('@')) {
                alert('الرجاء إدخال بريد إلكتروني صحيح.');
                return;
            }

            if (users.some(user => user.email === userEmail)) {
                alert('هذا البريد الإلكتروني موجود بالفعل لمستخدم آخر.');
                return;
            }

            users.push({ name: userName, email: userEmail, password: userPassword, mobile: userMobile, role: userRole });
            newUserNameInput.value = '';
            newUserEmailInput.value = '';
            newUserPasswordInput.value = '';
            newUserMobileInput.value = '';
            renderUserList();
            renderTransactions();
            renderExcelReport();
            renderNetworkExcelReport();
            updateDailyDetailSummary();
            renderOtherOperationsTable(); // Render other operations
        });

        function deleteUser(userEmailToDelete) {
            if (currentUser.role !== 'admin') {
                alert('ليس لديك صلاحية لحذف المستخدمين.');
                return;
            }
            if (currentUser.email === userEmailToDelete) {
                alert('لا يمكنك حذف المستخدم الذي سجلت دخوله حالياً.');
                return;
            }

            if (confirm(`هل أنت متأكد من حذف المستخدم "${userEmailToDelete}"؟ سيتم حذف جميع معاملاته.`)) {
                users = users.filter(user => user.email !== userEmailToDelete);
                transactions = transactions.filter(transaction => {
                    const associatedUser = users.find(u => u.name === transaction.userName);
                    return associatedUser && associatedUser.email !== userEmailToDelete;
                });
                renderUserList();
                renderTransactions();
                renderExcelReport();
                renderNetworkExcelReport();
                updateDailyDetailSummary();
                renderOtherOperationsTable(); // Render other operations
            }
        }

        changePasswordBtn.addEventListener('click', () => {
            const currentPassword = currentPasswordInput.value;
            const newPassword = newPasswordInput.value;
            const confirmNewPassword = confirmNewPasswordInput.value;
            const mobileForVerification = mobileForVerificationInput.value.trim();

            if (!currentPassword || !newPassword || !confirmNewPassword || !mobileForVerification) {
                alert('الرجاء ملء جميع حقول تغيير كلمة المرور.');
                return;
            }

            if (currentUser.password !== currentPassword) {
                alert('كلمة المرور الحالية غير صحيحة.');
                return;
            }

            if (newPassword.length < 6) {
                alert('كلمة المرور الجديدة يجب أن تكون 6 أحرف على الأقل.');
                return;
            }

            if (newPassword !== confirmNewPassword) {
                alert('كلمة المرور الجديدة وتأكيدها غير متطابقين.');
                return;
            }

            if (currentUser.mobile && currentUser.mobile !== mobileForVerification) {
                alert('رقم الجوال المدخل لا يتطابق مع الرقم المسجل.');
                return;
            }
            
            if (!currentUser.mobile && mobileForVerification) {
            } else if (!currentUser.mobile && !mobileForVerification) {
                 alert('الرجاء إدخال رقم الجوال المسجل للتحقق.');
                 return;
            }

            const userIndex = users.findIndex(u => u.email === currentUser.email);
            if (userIndex !== -1) {
                users[userIndex].password = newPassword;
                if (mobileForVerification && !users[userIndex].mobile) {
                    users[userIndex].mobile = mobileForVerification;
                }
                currentUser.password = newPassword;
                currentUser.mobile = users[userIndex].mobile;
                sessionStorage.setItem('currentUser', JSON.stringify(currentUser));
                saveToLocalStorage();
                alert('تم تغيير كلمة المرور بنجاح!');
                currentPasswordInput.value = '';
                newPasswordInput.value = '';
                confirmNewPasswordInput.value = '';
                mobileForVerificationInput.value = '';
            } else {
                alert('حدث خطأ: لم يتم العثور على المستخدم.');
            }
        });

        const today = new Date();
        const andYYYY = today.getFullYear();
        const mm = String(today.getMonth() + 1).padStart(2, '0');
        const dd = String(today.getDate()).padStart(2, '0');
        const todayFormatted = `${andYYYY}-${mm}-${dd}`;
        transactionDateInput.value = todayFormatted;
        specialNetworkDateInput.value = todayFormatted;
        otherOperationDateInput.value = todayFormatted; // Set date for other operations
        todayDateSpan.textContent = todayFormatted;
        dailyDetailDateSpan.textContent = todayFormatted;

        function updateSummary(filteredTrans = transactions) {
            let totalCash = 0;
            let totalNetwork = 0;
            let totalExpenses = 0;

            filteredTrans.forEach(transaction => {
                totalCash += transaction.cash;
                if (!transaction.excludeFromTotal) {
                    totalNetwork += transaction.network;
                }
                totalExpenses += transaction.expense;
            });

            const totalIncome = totalCash + totalNetwork;
            const netIncome = totalIncome - totalExpenses;
            const sharedIncome = netIncome > 0 ? netIncome / 2 : 0;

            totalCashSpan.textContent = totalCash.toFixed(2);
            totalNetworkSpan.textContent = totalNetwork.toFixed(2);
            totalExpensesSpan.textContent = totalExpenses.toFixed(2);
            totalNetSpan.textContent = netIncome.toFixed(2);
            shopShareSpan.textContent = sharedIncome.toFixed(2);
            workerShareSpan.textContent = sharedIncome.toFixed(2);
        }

        function updateDailySummary() {
            const todayTransactions = transactions.filter(t => t.date === todayFormatted);
            
            let dailyCash = 0;
            let dailyNetwork = 0;
            let dailyExpenses = 0;

            todayTransactions.forEach(transaction => {
                dailyCash += transaction.cash;
                if (!transaction.excludeFromTotal) {
                    dailyNetwork += transaction.network;
                }
                dailyExpenses += transaction.expense;
            });

            const dailyIncome = dailyCash + dailyNetwork;
            const dailyNetIncome = dailyIncome - dailyExpenses;
            const dailySharedIncome = dailyNetIncome > 0 ? dailyNetIncome / 2 : 0;

            todayCashSpan.textContent = dailyCash.toFixed(2);
            todayNetworkSpan.textContent = dailyNetwork.toFixed(2);
            todayExpensesSpan.textContent = dailyExpenses.toFixed(2);
            todayNetSpan.textContent = dailyNetIncome.toFixed(2);
            todayShopShareSpan.textContent = dailySharedIncome.toFixed(2);
            todayWorkerShareSpan.textContent = dailySharedIncome.toFixed(2);
        }

        function updateDailyDetailSummary() {
            dailyDetailCashSpan.textContent = '0';
            dailyDetailNetworkSpan.textContent = '0';
            dailyDetailTotalIncomeSpan.textContent = '0';
            dailyDetailHalfIncomeSpan.textContent = '0';
        }

        calculateDailyCashBtn.addEventListener('click', () => {
            const todayTransactions = transactions.filter(t => t.date === todayFormatted);
            let cashForToday = 0;
            todayTransactions.forEach(t => {
                cashForToday += t.cash;
            });
            dailyDetailCashSpan.textContent = cashForToday.toFixed(2);
            updateDailyDetailTotal();
        });

        calculateDailyNetworkBtn.addEventListener('click', () => {
            const todayTransactions = transactions.filter(t => t.date === todayFormatted);
            let networkForToday = 0;
            todayTransactions.forEach(t => {
                networkForToday += t.network;
            });
            dailyDetailNetworkSpan.textContent = networkForToday.toFixed(2);
            updateDailyDetailTotal();
        });

        function updateDailyDetailTotal() {
            const cashVal = parseFloat(dailyDetailCashSpan.textContent) || 0;
            const networkVal = parseFloat(dailyDetailNetworkSpan.textContent) || 0;
            const total = cashVal + networkVal;
            dailyDetailTotalIncomeSpan.textContent = total.toFixed(2);
            dailyDetailHalfIncomeSpan.textContent = (total / 2).toFixed(2);
        }

        function renderTransactions() {
            transactionsTableBody.innerHTML = '';
            const selectedUser = filterByUserSelect.value;
            let transactionsToDisplay = transactions;

            if (currentUser.role === 'user') {
                transactionsToDisplay = transactions.filter(t => t.userName === currentUser.name);
                filterByUserSelect.value = currentUser.name;
                filterByUserSelect.disabled = true;
            } else if (selectedUser !== 'all') {
                transactionsToDisplay = transactions.filter(t => t.userName === selectedUser);
                filterByUserSelect.disabled = false;
            } else {
                 filterByUserSelect.disabled = false;
            }

            transactionsToDisplay.forEach((transaction, index) => {
                const transactionTotal = (transaction.cash + transaction.network - transaction.expense).toFixed(2);
                let rowClass = '';
                let totalCellContent = transactionTotal;

                if (transaction.excludeFromTotal) {
                    rowClass = 'excluded-from-total';
                    totalCellContent = `${transactionTotal} (غير محسوب)`;
                }

                const originalIndex = transactions.findIndex(t =>
                    t.transactionId === transaction.transactionId
                );

                const row = transactionsTableBody.insertRow();
                row.className = rowClass;
                row.innerHTML = `
                    <td class="whitespace-nowrap">${originalIndex + 1}</td>
                    <td>${transaction.transactionId}</td>
                    <td class="whitespace-nowrap">${transaction.date}</td>
                    <td>${transaction.userName || '-'}</td>
                    <td>${transaction.cash.toFixed(2)}</td>
                    <td>${transaction.network.toFixed(2)}</td>
                    <td>${transaction.expense.toFixed(2)}</td>
                    <td>${totalCellContent}</td>
                    <td>${transaction.description || '-'}</td>
                    <td>
                        <button class="bg-red-500 hover:bg-red-700 text-white py-1 px-2 rounded text-sm" onclick="deleteTransaction(${originalIndex})">حذف</button>
                    </td>
                `;
            });
            updateSummary(transactionsToDisplay);
            updateDailySummary();
            updateDailyDetailSummary();
            saveToLocalStorage();
            renderExcelReport();
            renderNetworkExcelReport();
            renderOtherOperationsTable(); // Render other operations table as well
        }

        function getDayName(dateString) {
            const date = new Date(dateString + 'T12:00:00');
            return date.toLocaleDateString('ar-SA', { weekday: 'long' });
        }

        function renderExcelReport() {
            excelReportTableBody.innerHTML = '';
            const selectedUser = filterByUserSelect.value;
            let transactionsToDisplay = transactions;

            if (currentUser.role === 'user') {
                transactionsToDisplay = transactions.filter(t => t.userName === currentUser.name);
            } else if (selectedUser !== 'all') {
                transactionsToDisplay = transactions.filter(t => t.userName === selectedUser);
            }

            transactionsToDisplay.forEach((transaction, index) => {
                let transactionAmount = 0;
                if (!transaction.excludeFromTotal) {
                    transactionAmount = (transaction.cash + transaction.network - transaction.expense).toFixed(2);
                } else {
                    transactionAmount = '0.00 (مستبعد)';
                }
                
                const dayName = getDayName(transaction.date);

                const row = excelReportTableBody.insertRow();
                row.innerHTML = `
                    <td>${index + 1}</td>
                    <td>${transaction.transactionId}</td>
                    <td class="whitespace-nowrap">${transaction.date}</td>
                    <td>${dayName}</td>
                    <td>${transaction.userName || '-'}</td>
                    <td>${transactionAmount}</td>
                    <td>${transaction.description || '-'}</td>
                `;
            });
        }

        function renderNetworkExcelReport() {
            networkReportTableBody.innerHTML = '';
            const selectedUser = filterByUserSelect.value;
            let transactionsToDisplay = transactions;

            if (currentUser.role === 'user') {
                transactionsToDisplay = transactions.filter(t => t.userName === currentUser.name && t.network > 0);
            } else if (selectedUser !== 'all') {
                transactionsToDisplay = transactions.filter(t => t.userName === selectedUser && t.network > 0);
            } else {
                transactionsToDisplay = transactions.filter(t => t.network > 0);
            }

            transactionsToDisplay.forEach((transaction, index) => {
                const dayName = getDayName(transaction.date);
                let networkAmountDisplay = transaction.network.toFixed(2);
                if (transaction.excludeFromTotal) {
                    networkAmountDisplay += ' (غير محسوب بالإجمالي)';
                }

                const row = networkReportTableBody.insertRow();
                row.innerHTML = `
                    <td>${index + 1}</td>
                    <td>${transaction.transactionId}</td>
                    <td class="whitespace-nowrap">${transaction.date}</td>
                    <td>${dayName}</td>
                    <td>${transaction.userName || '-'}</td>
                    <td>${networkAmountDisplay}</td>
                    <td>${transaction.description || '-'}</td>
                `;
            });
        }

        // --- Other Operations Functions ---
        function renderOtherOperationsTable() {
            otherOperationsTableBody.innerHTML = '';
            otherOperationsNotesTextarea.value = otherOperationsNotes; // Update notes textarea
            otherOperationsTitleDisplay.textContent = otherOperationsTitle; // Update display title
            otherOperationsTitleInput.value = otherOperationsTitle; // Update input title

            otherOperations.forEach((operation, index) => {
                const dayName = getDayName(operation.date);
                const row = otherOperationsTableBody.insertRow();
                row.innerHTML = `
                    <td>${index + 1}</td>
                    <td>${operation.name || '-'}</td>
                    <td>${operation.operationNumber || '-'}</td>
                    <td class="whitespace-nowrap">${operation.date}</td>
                    <td>${dayName}</td>
                    <td>${operation.description || '-'}</td>
                    <td>
                        <button class="bg-red-500 hover:bg-red-700 text-white py-1 px-2 rounded text-sm" onclick="deleteOtherOperation(${operation.id})">حذف</button>
                    </td>
                `;
            });
            saveToLocalStorage();
        }

        addOtherOperationBtn.addEventListener('click', () => {
            const name = otherOperationNameInput.value.trim();
            const operationNumber = otherOperationNumberInput.value.trim();
            const date = otherOperationDateInput.value;
            const description = otherOperationDescriptionInput.value.trim();

            if (!name || !operationNumber || !date) {
                alert('الرجاء إدخال اسم العملية ورقم العملية والتاريخ.');
                return;
            }

            otherOperationCounter++;
            const newOperation = { id: otherOperationCounter, name, operationNumber, date, description };
            otherOperations.push(newOperation);

            otherOperationNameInput.value = '';
            otherOperationNumberInput.value = '';
            otherOperationDescriptionInput.value = '';
            // otherOperationDateInput.value = todayFormatted; // Keep date as today's date

            renderOtherOperationsTable();
        });

        function deleteOtherOperation(idToDelete) {
            if (confirm('هل أنت متأكد من حذف هذه العملية الأخرى؟')) {
                otherOperations = otherOperations.filter(op => op.id !== idToDelete);
                renderOtherOperationsTable();
            }
        }

        otherOperationsNotesTextarea.addEventListener('input', () => {
            otherOperationsNotes = otherOperationsNotesTextarea.value;
            saveToLocalStorage();
        });

        otherOperationsTitleDisplay.addEventListener('click', () => {
            otherOperationsTitleDisplay.classList.add('hidden');
            otherOperationsTitleInput.classList.remove('hidden');
            saveOtherOperationsTitleBtn.classList.remove('hidden');
            otherOperationsTitleInput.focus();
        });

        saveOtherOperationsTitleBtn.addEventListener('click', () => {
            const newTitle = otherOperationsTitleInput.value.trim();
            if (newTitle) {
                otherOperationsTitle = newTitle;
            } else {
                otherOperationsTitle = 'عمليات أخرى'; // Default if empty
            }
            otherOperationsTitleDisplay.textContent = otherOperationsTitle;
            otherOperationsTitleDisplay.classList.remove('hidden');
            otherOperationsTitleInput.classList.add('hidden');
            saveOtherOperationsTitleBtn.classList.add('hidden');
            saveToLocalStorage();
        });

        otherOperationsTitleInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                saveOtherOperationsTitleBtn.click();
            }
        });


        addTransactionBtn.addEventListener('click', () => {
            const date = transactionDateInput.value;
            const cash = parseFloat(cashAmountInput.value) || 0;
            const network = parseFloat(networkAmountInput.value) || 0;
            const excludeFromTotal = excludeFromTotalCheckbox.checked;
            const expense = parseFloat(expenseAmountInput.value) || 0;
            const description = descriptionInput.value.trim();
            const responsibleUser = responsibleUserSelect.value;

            if (!responsibleUser) {
                alert('الرجاء اختيار المستخدم المسؤول عن هذه المعاملة.');
                return;
            }

            if (cash === 0 && network === 0 && expense === 0) {
                alert('الرجاء إدخال مبلغ للكاش أو الشبكة أو مصروف.');
                return;
            }

            transactionCounter++;
            const newTransaction = { transactionId: transactionCounter, date, userName: responsibleUser, cash, network, excludeFromTotal, expense, description };
            transactions.push(newTransaction);

            cashAmountInput.value = '';
            networkAmountInput.value = '';
            excludeFromTotalCheckbox.checked = false;
            expenseAmountInput.value = '';
            descriptionInput.value = '';
            
            renderTransactions();
            renderExcelReport();
            renderNetworkExcelReport();
            updateDailyDetailSummary();
            renderOtherOperationsTable(); // Re-render other operations table on any transaction change
        });

        addSpecialNetworkBtn.addEventListener('click', () => {
            const date = specialNetworkDateInput.value;
            const network = parseFloat(specialNetworkAmountInput.value) || 0;
            const description = specialNetworkDescriptionInput.value.trim();
            const responsibleUser = specialNetworkUserSelect.value;

            if (!responsibleUser) {
                alert('الرجاء اختيار المستخدم المسؤول عن عملية الشبكة الخاصة.');
                return;
            }

            if (network === 0) {
                alert('الرجاء إدخال مبلغ لعملية الشبكة الخاصة.');
                return;
            }

            transactionCounter++;
            const newTransaction = { transactionId: transactionCounter, date, userName: responsibleUser, cash: 0, network: network, excludeFromTotal: true, expense: 0, description: description };
            transactions.push(newTransaction);

            specialNetworkAmountInput.value = '';
            specialNetworkDescriptionInput.value = '';

            renderTransactions();
            renderExcelReport();
            renderNetworkExcelReport();
            updateDailyDetailSummary();
            renderOtherOperationsTable(); // Re-render other operations table
        });

        function deleteTransaction(originalIndex) {
            if (currentUser.role === 'user' && transactions[originalIndex].userName !== currentUser.name) {
                alert('ليس لديك صلاحية لحذف معاملات المستخدمين الآخرين.');
                return;
            }

            if (confirm('هل أنت متأكد من حذف هذه المعاملة؟')) {
                transactions.splice(originalIndex, 1);
                renderTransactions();
                renderExcelReport();
                renderNetworkExcelReport();
                updateDailyDetailSummary();
                renderOtherOperationsTable(); // Re-render other operations table
            }
        }

        const sections = [
            addTransactionSection,
            addSpecialNetworkSection,
            transactionsLogSection,
            excelReportSection,
            networkReportSection,
            changePasswordSection,
            adminSection,
            dailyIncomeSection,
            otherOperationsSection // Include new section
        ];

        function showSection(sectionIdToShow) {
            sections.forEach(section => {
                if (section.id === sectionIdToShow) {
                    section.classList.remove('hidden');
                } else {
                    section.classList.add('hidden');
                }
            });
        }

        document.querySelectorAll('.nav-button').forEach(button => {
            button.addEventListener('click', (event) => {
                const sectionId = event.target.dataset.section;
                if (sectionId === 'adminSection' && currentUser.role !== 'admin') {
                    alert('ليس لديك صلاحية الوصول إلى إدارة المستخدمين.');
                    return;
                }
                showSection(sectionId);
            });
        });

        enhanceDescriptionBtn.addEventListener('click', async () => {
            const currentDescription = descriptionInput.value.trim();
            if (!currentDescription) {
                alert('الرجاء إدخال وصف مبدئي لتحسينه.');
                return;
            }

            descriptionLoading.classList.remove('hidden');
            enhanceDescriptionBtn.disabled = true;

            const prompt = `Expand on this financial transaction description and suggest a category for it (e.g., 'Office Supplies', 'Utilities', 'Service Fee', 'Tuition Payment', 'Book Sale', 'Printing Service', 'Consulting Fee'). Keep the response concise and directly usable as a description. Original description: "${currentDescription}"`;
            
            const enhancedText = await callGeminiAPI(prompt);
            descriptionInput.value = enhancedText;

            descriptionLoading.classList.add('hidden');
            enhanceDescriptionBtn.disabled = false;
        });

        getFinancialInsightBtn.addEventListener('click', async () => {
            if (currentUser.role !== 'admin') {
                alert('ليس لديك صلاحية للحصول على رؤى مالية.');
                return;
            }

            financialInsightLoading.classList.remove('hidden');
            getFinancialInsightBtn.disabled = true;
            financialInsightOutput.classList.add('hidden');

            const totalCash = totalCashSpan.textContent;
            const totalNetwork = totalNetworkSpan.textContent;
            const totalExpenses = totalExpensesSpan.textContent;
            const totalNet = totalNetSpan.textContent;

            const prompt = `Given these financial summaries for a student services office: Total Cash Income: ${totalCash} ريال, Total Network Income: ${totalNetwork} ريال, Total Expenses: ${totalExpenses} ريال, Net Income: ${totalNet} ريال. Provide a very brief, high-level financial insight or suggestion for the business owner. Keep it concise, professional, and actionable if possible.`;
            
            const insight = await callGeminiAPI(prompt);
            financialInsightOutput.textContent = insight;
            financialInsightOutput.classList.remove('hidden');

            financialInsightLoading.classList.add('hidden');
            getFinancialInsightBtn.disabled = false;
        });


        loginBtn.addEventListener('click', login);
        logoutBtn.addEventListener('click', logout);
        filterByUserSelect.addEventListener('change', renderTransactions);

        copyAppLinkBtn.addEventListener('click', () => {
            navigator.clipboard.writeText(window.location.href).then(() => {
                alert('تم نسخ رابط التطبيق إلى الحافظة!');
            }).catch(err => {
                console.error('فشل في نسخ الرابط: ', err);
                alert('فشل في نسخ الرابط. يرجى النسخ يدوياً من شريط العنوان.');
            });
        });

        loadFromLocalStorage();
        
        if (users.length === 0) {
            users.push({ name: 'مدير النظام', email: 'admin@example.com', password: 'password', mobile: '05xxxxxxxx', role: 'admin' });
            saveToLocalStorage();
        }
        
        checkLoginStatus();
    </script>
</body>
</html>
