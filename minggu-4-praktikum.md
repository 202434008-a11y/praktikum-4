# Praktikum Minggu 4 — Read-only Laravel API

## Resource

Book

## Endpoint

- `GET /api/books`
- `GET /api/books/{book}`

## Verification

- **200 list:** Berhasil. Endpoint `GET /api/books` telah didaftarkan pada routing API. Verifikasi response aktual dilakukan melalui Postman.
- **200 detail:** Berhasil. Endpoint `GET /api/books/{book}` telah didaftarkan pada routing API. Verifikasi response aktual dilakukan melalui Postman.
- **404 not found:** Berhasil jika request dengan ID yang tidak tersedia menghasilkan status `404 Not Found`. Verifikasi dilakukan melalui Postman dengan URL `/api/books/999999`.

## Contract Comparison

Actual response dibandingkan dengan API contract Minggu 3 berdasarkan method, path, status code, struktur body, nama field, dan tipe data.

Endpoint yang diperiksa:

- `GET /api/books` respons `200 OK` dan daftar buku.
[
    {
        "id": 1,
        "title": "Clean Code",
        "isbn": "9780132350884",
        "available": 1,
        "created_at": "2026-10-08T07:05:47.000000Z",
        "updated_at": "2026-10-08T07:05:47.000000Z"
    },
    {
        "id": 2,
        "title": "The Pragmatic Programmer",
        "isbn": "9780135957059",
        "available": 1,
        "created_at": "2026-10-08T07:05:47.000000Z",
        "updated_at": "2026-10-08T07:05:47.000000Z"
    }
]
- `GET /api/books/{book}`  ID yang tersedia merespons `200 OK` dan satu data buku.
{
    "id": 1,
    "title": "Clean Code",
    "isbn": "9780132350884",
    "available": 1,
    "created_at": "2026-10-08T07:05:47.000000Z",
    "updated_at": "2026-10-08T07:05:47.000000Z"
}

- `GET /api/books/{book}`ID yang tidak tersedia merespons `404 Not Found`.
{
    "message": "No query results for model [App\\Models\\Book] 999999",
    "exception": "Symfony\\Component\\HttpKernel\\Exception\\NotFoundHttpException",
    "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Foundation\\Exceptions\\Handler.php",
    "line": 773,
    "trace": [
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Foundation\\Exceptions\\Handler.php",
            "line": 721,
            "function": "prepareException",
            "class": "Illuminate\\Foundation\\Exceptions\\Handler",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Routing\\Pipeline.php",
            "line": 51,
            "function": "render",
            "class": "Illuminate\\Foundation\\Exceptions\\Handler",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Pipeline\\Pipeline.php",
            "line": 224,
            "function": "handleException",
            "class": "Illuminate\\Routing\\Pipeline",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Pipeline\\Pipeline.php",
            "line": 137,
            "function": "{closure:{closure:Illuminate\\Pipeline\\Pipeline::carry():194}:195}",
            "class": "Illuminate\\Pipeline\\Pipeline",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Routing\\Router.php",
            "line": 833,
            "function": "then",
            "class": "Illuminate\\Pipeline\\Pipeline",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Routing\\Router.php",
            "line": 812,
            "function": "runRouteWithinStack",
            "class": "Illuminate\\Routing\\Router",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Routing\\Router.php",
            "line": 776,
            "function": "runRoute",
            "class": "Illuminate\\Routing\\Router",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Routing\\Router.php",
            "line": 765,
            "function": "dispatchToRoute",
            "class": "Illuminate\\Routing\\Router",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Foundation\\Http\\Kernel.php",
            "line": 200,
            "function": "dispatch",
            "class": "Illuminate\\Routing\\Router",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Pipeline\\Pipeline.php",
            "line": 180,
            "function": "{closure:Illuminate\\Foundation\\Http\\Kernel::dispatchToRouter():197}",
            "class": "Illuminate\\Foundation\\Http\\Kernel",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Foundation\\Http\\Middleware\\TransformsRequest.php",
            "line": 21,
            "function": "{closure:Illuminate\\Pipeline\\Pipeline::prepareDestination():178}",
            "class": "Illuminate\\Pipeline\\Pipeline",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Foundation\\Http\\Middleware\\ConvertEmptyStringsToNull.php",
            "line": 31,
            "function": "handle",
            "class": "Illuminate\\Foundation\\Http\\Middleware\\TransformsRequest",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Pipeline\\Pipeline.php",
            "line": 219,
            "function": "handle",
            "class": "Illuminate\\Foundation\\Http\\Middleware\\ConvertEmptyStringsToNull",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Foundation\\Http\\Middleware\\TransformsRequest.php",
            "line": 21,
            "function": "{closure:{closure:Illuminate\\Pipeline\\Pipeline::carry():194}:195}",
            "class": "Illuminate\\Pipeline\\Pipeline",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Foundation\\Http\\Middleware\\TrimStrings.php",
            "line": 51,
            "function": "handle",
            "class": "Illuminate\\Foundation\\Http\\Middleware\\TransformsRequest",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Pipeline\\Pipeline.php",
            "line": 219,
            "function": "handle",
            "class": "Illuminate\\Foundation\\Http\\Middleware\\TrimStrings",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Http\\Middleware\\ValidatePostSize.php",
            "line": 27,
            "function": "{closure:{closure:Illuminate\\Pipeline\\Pipeline::carry():194}:195}",
            "class": "Illuminate\\Pipeline\\Pipeline",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Pipeline\\Pipeline.php",
            "line": 219,
            "function": "handle",
            "class": "Illuminate\\Http\\Middleware\\ValidatePostSize",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Foundation\\Http\\Middleware\\PreventRequestsDuringMaintenance.php",
            "line": 110,
            "function": "{closure:{closure:Illuminate\\Pipeline\\Pipeline::carry():194}:195}",
            "class": "Illuminate\\Pipeline\\Pipeline",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Pipeline\\Pipeline.php",
            "line": 219,
            "function": "handle",
            "class": "Illuminate\\Foundation\\Http\\Middleware\\PreventRequestsDuringMaintenance",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Http\\Middleware\\HandleCors.php",
            "line": 74,
            "function": "{closure:{closure:Illuminate\\Pipeline\\Pipeline::carry():194}:195}",
            "class": "Illuminate\\Pipeline\\Pipeline",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Pipeline\\Pipeline.php",
            "line": 219,
            "function": "handle",
            "class": "Illuminate\\Http\\Middleware\\HandleCors",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Http\\Middleware\\TrustProxies.php",
            "line": 58,
            "function": "{closure:{closure:Illuminate\\Pipeline\\Pipeline::carry():194}:195}",
            "class": "Illuminate\\Pipeline\\Pipeline",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Pipeline\\Pipeline.php",
            "line": 219,
            "function": "handle",
            "class": "Illuminate\\Http\\Middleware\\TrustProxies",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Foundation\\Http\\Middleware\\InvokeDeferredCallbacks.php",
            "line": 22,
            "function": "{closure:{closure:Illuminate\\Pipeline\\Pipeline::carry():194}:195}",
            "class": "Illuminate\\Pipeline\\Pipeline",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Pipeline\\Pipeline.php",
            "line": 219,
            "function": "handle",
            "class": "Illuminate\\Foundation\\Http\\Middleware\\InvokeDeferredCallbacks",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Http\\Middleware\\ValidatePathEncoding.php",
            "line": 28,
            "function": "{closure:{closure:Illuminate\\Pipeline\\Pipeline::carry():194}:195}",
            "class": "Illuminate\\Pipeline\\Pipeline",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Pipeline\\Pipeline.php",
            "line": 219,
            "function": "handle",
            "class": "Illuminate\\Http\\Middleware\\ValidatePathEncoding",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Pipeline\\Pipeline.php",
            "line": 137,
            "function": "{closure:{closure:Illuminate\\Pipeline\\Pipeline::carry():194}:195}",
            "class": "Illuminate\\Pipeline\\Pipeline",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Foundation\\Http\\Kernel.php",
            "line": 175,
            "function": "then",
            "class": "Illuminate\\Pipeline\\Pipeline",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Foundation\\Http\\Kernel.php",
            "line": 144,
            "function": "sendRequestThroughRouter",
            "class": "Illuminate\\Foundation\\Http\\Kernel",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Foundation\\Application.php",
            "line": 1228,
            "function": "handle",
            "class": "Illuminate\\Foundation\\Http\\Kernel",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\public\\index.php",
            "line": 20,
            "function": "handleRequest",
            "class": "Illuminate\\Foundation\\Application",
            "type": "->"
        },
        {
            "file": "C:\\Users\\labsi\\Herd\\praktikum4\\vendor\\laravel\\framework\\src\\Illuminate\\Foundation\\resources\\server.php",
            "line": 23,
            "function": "require_once"
        }
    ]
}


## Evidence

Nama request Postman dan ringkasan hasil:

1. **List Books**
   - Request: `GET http://127.0.0.1:8000/api/books`
   - Response: `200 OK`, daftar buku dalam response JSON.

2. **Show Book**
   - Request: `GET http://127.0.0.1:8000/api/books/1`
   - Response: `200 OK`, satu data buku dalam response JSON.
   

3. **Book Not Found**
   - Request: `GET http://127.0.0.1:8000/api/books/999999`
   - Response: `404 Not Found`.

Postman collection: 

API contract Minggu 3: [Tuliskan path atau tautan API contract yang digunakan untuk perbandingan].

Commit GitHub terkait: [Tempelkan tautan commit yang memuat perubahan Praktikum Minggu 4].

Repository GitHub public: [Tempelkan tautan repository].

Jangan memasukkan token, credential, password, cookie, API key, atau secret ke dalam dokumentasi maupun Postman collection.

## Referensi

- Panduan Praktikum 4 — *Endpoint Read-only dengan Laravel*.
- Laravel Documentation — Routing: https://laravel.com/docs/routing
- Laravel Documentation — Controllers: https://laravel.com/docs/controllers
- Laravel Documentation — Eloquent: https://laravel.com/docs/eloquent
- Laravel Documentation — Migrations: https://laravel.com/docs/migrations
- Laravel Documentation — Database Seeding: https://laravel.com/docs/seeding
- Postman Documentation — Sending requests: https://learning.postman.com/docs/sending-requests/requests/

## Deklarasi Penggunaan AI

AI digunakan sebagai alat bantu untuk menyusun dan merapikan dokumentasi. Implementasi kode, membantu meluruskan typo yang ada di dalam dokumentasi, dan memberikan saran pada kode. Tidak ada pengujian yang dilakukan menggunakan AI. 