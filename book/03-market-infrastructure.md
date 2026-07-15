# Infrastruktur Pasar Aset Kripto Indonesia

## Mengapa Indonesia Mewajibkan Pemisahan Bursa, Kliring, dan Kustodian

Indonesia menerapkan model *segregation of function* sebagai prinsip non-negosiasi dalam arsitektur pasar aset kripto. Pemisahan ini bukan sekadar rekomendasi tata kelola — melainkan persyaratan perizinan yang diatur dalam POJK 27/2024 dan dipertegas dalam POJK 23/2025.[^2][^3]

Logika regulator di balik pemisahan ini bersumber dari dua pengalaman. Pertama, kasus FTX (2022) membuktikan bahwa ketika bursa, *market maker*, dan kustodian berada dalam satu entitas atau grup yang tidak terawasi secara independen, dana nasabah dapat dipindahkan tanpa sepengetahuan regulator. Kedua, pasar modal Indonesia telah membuktikan bahwa pemisahan BEI (bursa), KPEI (kliring), dan KSEI (kustodian) selama puluhan tahun menciptakan stabilitas sistemik. OJK menerapkan logika yang sama pada aset kripto.

Dengan pemisahan ini, OJK memastikan tidak ada satu pun entitas yang memiliki kendali penuh atas pencatatan order, penyelesaian dana, dan penyimpanan aset secara simultan. Secara struktural:

- Dana fiat nasabah wajib disimpan di lembaga kliring, bukan di PAKD.
- Aset kripto nasabah wajib disimpan di lembaga kustodian, bukan di PAKD.
- PAKD hanya mencatat hak tagih (*book entry*) — saldo yang dilihat konsumen di aplikasi adalah catatan, bukan kepemilikan langsung.

Bagi seorang founder, pemahaman terhadap struktur ini sangat krusial karena mempengaruhi cara Anda merancang model bisnis, hubungan kontraktual dengan mitra, hingga strategi pengajuan izin ke OJK.

## Sejarah Evolusi: Dari Bappebti ke OJK

Sebelum 2018, tidak ada kerangka hukum khusus untuk aset kripto di Indonesia. Exchange beroperasi sebagai perusahaan biasa tanpa kewajiban perizinan sektoral. Pada 2018, Bappebti — sebagai otoritas perdagangan berjangka komoditi di bawah Kementerian Perdagangan — menerbitkan Peraturan Menteri Perdagangan Nomor 99 Tahun 2018, yang mengkategorikan aset kripto sebagai komoditi yang dapat diperdagangkan di bursa berjangka. Keputusan ini bersifat pragmatis: memberikan payung hukum sementara bagi industri yang saat itu belum memiliki tempat dalam rezim jasa keuangan.

Di bawah Bappebti, ekosistem perdagangan aset kripto mulai terbentuk. Peraturan Bappebti Nomor 8 Tahun 2021 memperkenalkan kewajiban pencatatan dan pelaporan. Puncaknya pada Juli 2023, Bappebti menetapkan tiga SRO pertama: PT Bursa Komoditi Nusantara (CFX) sebagai bursa, PT Kliring Berjangka Indonesia (KBI) sebagai lembaga kliring, dan PT Tennet Depository sebagai kustodian pertama.[^16][^17]

Namun, arah kebijakan berubah dengan disahkannya UU No. 4 Tahun 2023 tentang Pengembangan dan Penguatan Sektor Keuangan (UU P2SK). Undang-undang ini secara fundamental mengubah status aset kripto: dari komoditi yang diatur oleh kementerian perdagangan menjadi instrumen keuangan yang diawasi oleh otoritas jasa keuangan. Pasal 312 UU P2SK memberikan batas waktu 24 bulan sejak pengundangan (12 Januari 2023) untuk menyelesaikan peralihan dari Bappebti ke OJK.

Pada 10 Januari 2025, Berita Acara Serah Terima (BAST) ditandatangani. OJK resmi memegang kendali penuh atas pengaturan dan pengawasan aset kripto.[^6] Perubahan ini membawa perbedaan pendekatan yang material:

| Aspek | Bappebti (2018–2025) | OJK (2025–sekarang) |
|-------|----------------------|---------------------|
| Status aset | Komoditi | Instrumen keuangan |
| Fokus pengaturan | Teknis perdagangan, pasar berjangka | Tata kelola, risiko sistemik, perlindungan konsumen |
| Istilah pelaku | Pedagang Fisik Aset Kripto (PFAK) | Pedagang Aset Keuangan Digital (PAKD) |
| Kerangka hukum | Peraturan Menteri | Undang-undang (UU P2SK) + POJK |
| Sanksi pidana | Tidak diatur secara eksplisit | Penjara 5–10 tahun, denda hingga Rp1 triliun (Pasal 304 UU P2SK)[^4] |

Bagi founder, peralihan ini berarti bahwa setiap rencana bisnis tokenisasi kini harus memenuhi standar yang setara dengan lembaga jasa keuangan. Persyaratan *fit and proper test* bagi pihak utama (POJK 16/2025)[^27] dan kewajiban rencana bisnis (SEOJK 34/2025)[^26] adalah konsekuensi langsung dari perubahan rezim ini.

## Bursa: CFX dan ICEX

Bursa adalah penyelenggara sistem perdagangan. Dalam kerangka POJK 27/2024, Penyelenggara Bursa Aset Keuangan Digital memiliki kewenangan untuk menetapkan Daftar Aset Kripto yang dapat diperdagangkan, mengawasi anggota bursa (PAKD), menetapkan peraturan dan tata tertib perdagangan, memelihara integritas pasar, dan melaporkan data transaksi ke OJK.[^5]

Indonesia memiliki dua bursa berizin hingga Juli 2026. Setiap bursa memiliki anggota PAKD yang sama dalam beberapa kasus, namun perbedaan arsitektur dan fokus bisnisnya relevan bagi founder.

### CFX (PT Central Finansial X)

CFX adalah bursa pertama, didirikan pada 2023 dengan persetujuan Bappebti (Keputusan No. 01/BAPPEBTI/SP-BBAK/07/2023) dan dikonfirmasi izin oleh OJK melalui S-7/D.07/2025 per 1 Februari 2025.[^4][^16]

CFX tidak melayani konsumen secara langsung. CFX melayani PAKD sebagai anggota bursa. Seluruh order dari konsumen PAKD wajib dicocokkan melalui sistem yang disediakan CFX. CFX menyelenggarakan perdagangan *spot* dan derivatif kripto. Sepanjang 2025, nilai transaksi derivatif di CFX mencapai Rp64,16 triliun dengan 178 kontrak aktif.[^8]

CFX berada di bawah PT Indokripto Koin Semesta Tbk (COIN) yang melantai di Bursa Efek Indonesia pada Juli 2025.[^9] Implikasinya: CFX menghadapi pengawasan ganda — langsung oleh OJK IAKD dan tidak langsung oleh OJK Pasar Modal melalui induk usahanya. Bagi founder yang akan menjadi anggota bursa CFX, hal ini berarti bahwa tata kelola dan pelaporan keuangan harus memenuhi standar ganda.

Hingga pertengahan 2026, CFX memiliki sekitar 30 anggota, di mana 25 telah berstatus PAKD.[^10] Daftar anggota CFX yang berstatus PAKD dapat diakses melalui portal OJK. Seorang founder yang ingin menjadi PAKD harus terlebih dahulu menjadi anggota bursa.

### ICEX (PT Fortuna Integritas Mandiri)

ICEX adalah bursa kedua, mendapatkan izin OJK pada 5 Januari 2026 (KEP-2/D.07/2026)[^12] dan resmi diluncurkan pada 2 April 2026. ICEX didukung pendanaan Rp1 triliun dari 11 PAKD yang juga menjadi pemegang saham dan anggota bursa.[^14][^30]

Yang membedakan ICEX secara fundamental adalah pendekatan arsitekturnya. ICEX Group mengoperasikan tiga entitas terintegrasi dalam satu grup: ICEX (bursa), CACI (kliring), dan ICC (kustodian). Model ini memberikan pengalaman *end-to-end* bagi anggota bursa — proses perizinan, konektivitas teknis, dan rekonsiliasi dapat dilakukan dalam satu kelompok usaha.

Bagi founder, ICEX menawarkan dua keunggulan spesifik. Pertama, ICEX secara eksplisit menyebut tokenisasi RWA sebagai target produk utama.[^13][^14] Jika aset tokenisasi yang Anda terbitkan memerlukan pendekatan *listing* yang berbeda dari kripto konvensional, ICEX kemungkinan memiliki *framework* yang lebih siap dibandingkan bursa yang melayani kripto pada umumnya. Kedua, struktur grup terintegrasi menyederhanakan hubungan kontraktual — Anda cukup menjalin kerja sama dengan satu grup untuk mengakses bursa, kliring, dan kustodian.

Perlu dicatat bahwa model grup terintegrasi tidak menghilangkan kewajiban pemisahan fungsi. Ketiga entitas ICEX Group tetap memiliki izin OJK terpisah, kewajiban pelaporan independen, dan pengawasan yang terpisah secara hukum.

## Lembaga Kliring

Lembaga Kliring Penjaminan dan Penyelesaian memiliki dua fungsi utama: (a) penjaminan — menjamin bahwa setiap transaksi yang telah dicocokkan oleh bursa akan diselesaikan; dan (b) penyelesaian — memproses perpindahan dana fiat antar PAKD.

Fungsi penjaminan inilah yang membedakan ekosistem Indonesia dari banyak yurisdiksi lain. Jika sebuah PAKD gagal memenuhi kewajibannya terhadap nasabah, lembaga kliring yang menjamin penyelesaian — bukan bursa dan bukan PAKD itu sendiri. Bagi founder, ini berarti bahwa risiko gagal bayar rekanan (*counterparty risk*) telah dipindahkan dari PAKD ke lembaga kliring yang memiliki kapitalisasi lebih besar dan diawasi OJK secara langsung.

Syarat pendirian lembaga kliring mencerminkan besarnya tanggung jawab ini: modal disetor minimal Rp500 miliar, ekuitas minimal 80% dari modal disetor, dan sertifikasi ISO 27001.[^22]

Hingga Juli 2026, terdapat dua lembaga kliring berizin:[^4]

### PT Kliring Komoditi Indonesia (KKI)

KKI melayani ekosistem CFX dengan tanda berizin S-6/D.07/2025.[^4] Sejarahnya patut dicatat: pada Juli 2023, Bappebti menunjuk PT Kliring Berjangka Indonesia (KBI) — BUMN Kementerian Perdagangan — sebagai lembaga kliring pertama. Namun dalam transisi ke OJK, KBI tidak melanjutkan peran tersebut. KKI, yang terafiliasi dengan grup CFX/COIN, mengambil alih fungsi kliring untuk ekosistem CFX.

KKI menyimpan dana fiat nasabah, melakukan rekonsiliasi aset harian dengan ICC (kustodian), dan memastikan setiap transaksi terselesaikan secara tertib. Jika terjadi gagal bayar anggota, KKI bertindak sebagai pihak yang menjamin penyelesaian.[^15] Bagi founder, KKI adalah mitra yang harus Anda hubungkan secara sistem — seluruh kewajiban penyetoran dan penarikan dana nasabah harus melalui sistem KKI, bukan melalui rekening PAKD.

### PT Pranata Karya Solusi (CACI)

CACI — Crypto Asset Clearing International — melayani ekosistem ICEX dengan izin KEP-12/D.07/2026 per 2 Maret 2026.[^21] Fungsinya identik dengan KKI, namun melayani anggota ICEX. Kehadiran dua lembaga kliring menciptakan redundansi sistemik: jika satu lembaga kliring mengalami kegagalan, yang lain tetap beroperasi.

## Lembaga Kustodian

Pengelola Tempat Penyimpanan Aset Keuangan Digital (kustodian) adalah lembaga yang menyimpan, memelihara, mengawasi, dan menyerahkan aset kripto. Dalam kerangka OJK, kustodian adalah salah satu pilar paling penting karena menjawab pertanyaan yang selalu diajukan oleh auditor, bank, dan investor institusional: "Di mana aset disimpan dan bagaimana kepastian hukumnya?"

Kustodian wajib menyimpan paling sedikit 70% dari total aset kripto nasabah dalam *cold storage*. Ketentuan ini bersifat prudensial — memastikan bahwa mayoritas aset tidak terpapar risiko peretasan atau kegagalan operasional PAKD.[^19][^25]

Bagi founder, kustodian memiliki implikasi teknis dan hukum yang signifikan:

- **Teknis**: Kontrak pintar dan token yang Anda terbitkan harus kompatibel dengan sistem kustodian. Jika kustodian menggunakan teknologi MPC atau *multi-signature wallet* tertentu, token Anda harus mendukung mekanisme tersebut.
- **Hukum**: Perjanjian kustodian akan menjadi dokumen hukum utama yang mengatur tanggung jawab dan batas kewajiban jika terjadi kehilangan aset. Founder harus memastikan perjanjian ini diperiksa oleh *legal counsel* yang memahami aset digital.

Hingga Juli 2026, terdapat tiga kustodian berizin:[^4][^32]

### PT Kustodian Koin Indonesia (ICC)

ICC — Indonesia Coin Custodian — adalah kustodian pertama di Indonesia. Mendapat persetujuan Bappebti pada Desember 2023 (Keputusan No. 02/BAPPEBTI/SP-PTPAK/12/2023) dan izin OJK S-5/D.07/2025 per 1 Februari 2025.[^4][^18]

ICC melayani ekosistem CFX dan sejak April 2026 juga melayani ICEX. ICC menggunakan teknologi MPC dan *cold wallet*, serta melakukan rekonsiliasi harian dengan KKI dan CFX. ICC menyatakan kesiapan menerima aset tokenisasi sebagai objek kustodi — pernyataan yang relevan bagi founder yang menerbitkan RWA tokenized.[^19]

### PT Tennet Depository Indonesia

Tennet adalah kustodian yang mendapat izin pada era Bappebti (Juli 2023) dan dikonfirmasi OJK dengan S-33/D.07/2025 per 1 Juli 2025.[^4] Tennet tetap tercatat dalam whitelist OJK sebagai kustodian berizin, meskipun pemberitaan publiknya terbatas. Founder yang mempertimbangkan Tennet sebagai mitra kustodian perlu melakukan uji tuntas (*due diligence*) sendiri terhadap kesiapan operasionalnya.

### PT Arganis Konsultindo Utama

Arganis mendapatkan izin OJK pada 3 Maret 2026 melalui PENG-4/IK.01/2026.[^20] Sebagai entitas yang baru mendapatkan izin, founder perlu memantau perkembangan layanannya.

## Pedagang Aset Keuangan Digital (PAKD)

PAKD adalah entitas yang menjadi anggota bursa dan melayani konsumen akhir. Istilah "Pedagang" dalam PAKD — berbeda dengan "Pedagang Fisik Aset Kripto" (PFAK) di era Bappebti — mencerminkan status baru sebagai penyelenggara jasa keuangan, bukan pedagang komoditi. Perbedaan ini membawa konsekuensi regulasi yang material.

Untuk menjadi PAKD, sebuah entitas harus melalui proses perizinan OJK yang mencakup:

- **Penilaian Kemampuan dan Kepatutan** (*fit and proper test*) bagi direksi, komisaris, dan pemegang saham pengendali — diatur dalam POJK 16/2025.[^27]
- **Rencana Bisnis** yang disetujui OJK — diatur dalam SEOJK 34/2025.[^26]
- **Program APU PPT** (Anti Pencucian Uang dan Pencegahan Pendanaan Terorisme) — diatur dalam SEOJK 16/2025.[^33]
- **Konektivitas sistem** dengan bursa yang dipilih, lembaga kliring, dan kustodian.

Hingga Mei 2026, OJK mencatat 26 PAKD berizin dan beberapa CPAKD (Calon PAKD) yang masih dalam masa transisi.[^22] Daftar lengkap diterbitkan secara berkala di portal OJK dan menjadi rujukan tunggal untuk memverifikasi legalitas platform.

Bagi founder yang tidak ingin menjadi PAKD, alternatifnya adalah bekerja sama dengan PAKD yang sudah ada sebagai *issuer* atau penerbit aset tokenisasi. Dalam skema ini, PAKD menjadi saluran distribusi dan kepatuhan, sementara founder fokus pada pengelolaan aset dasar (*underlying asset*) dan penerbitan token.

## Alur Transaksi dari Perspektif Founder

Memahami alur transaksi penting bukan untuk kepentingan teknis semata, melainkan untuk merancang sistem, perjanjian, dan prosedur operasional yang akan diaudit oleh OJK dan auditor eksternal.

**1. Setoran dana fiat.** Nasabah mentransfer rupiah ke rekening PAKD. PAKD wajib meneruskan dana tersebut ke lembaga kliring secara sistemik. PAKD hanya mencatat saldo secara nominal. Dari perspektif audit, yang diperiksa adalah bukti penerusan dana — bukan saldo di rekening PAKD.

**2. Setoran aset kripto.** Nasabah mengirim aset kripto ke alamat yang disediakan PAKD. PAKD wajib meneruskan aset tersebut ke *wallet* kustodian yang telah ditentukan. Aset yang disimpan di kustodian harus tercatat secara terpisah dari aset operasional PAKD.

**3. Order dan eksekusi.** Order dari nasabah diteruskan oleh PAKD ke sistem bursa. Bursa mencocokkan order antar-PAKD. Tahap ini terjadi dalam hitungan detik.

**4. Kliring dan penyelesaian (T+0).** Setelah eksekusi, lembaga kliring memproses perpindahan dana fiat dan kustodian memproses perpindahan aset kripto. Di Indonesia, penyelesaian dilakukan secara *real-time* pada hari yang sama.

**5. Rekonsiliasi harian.** Setiap akhir hari, bursa, lembaga kliring, dan kustodian melakukan rekonsiliasi untuk memverifikasi bahwa seluruh transaksi yang tercatat di bursa sesuai dengan pergerakan dana di kliring dan pergerakan aset di kustodian. Jika terdapat ketidaksesuaian, PAKD wajib melakukan penambahan aset dalam waktu yang ditentukan oleh bursa. Prosedur rekonsiliasi ini menjadi salah satu area yang paling diperiksa dalam audit kepatuhan OJK.[^24][^25][^31]

Dari sudut pandang founder, tahap rekonsiliasi adalah titik di mana sistem Anda harus memiliki *audit trail* yang lengkap. Setiap perbedaan saldo — sekecil apa pun — harus dapat dijelaskan dan dilacak.

## Tanggung Jawab Masing-Masing Peserta

**OJK** sebagai regulator utama:[^2][^6]

- Menerbitkan dan mencabut izin Penyelenggara Perdagangan Aset Keuangan Digital.
- Melakukan pengawasan kepatuhan melalui pemeriksaan langsung dan tidak langsung.
- Menetapkan kebijakan makroprudensial untuk mencegah risiko sistemik.
- Menerapkan sanksi administratif hingga pidana (Pasal 304 UU P2SK).[^4]
- Menetapkan whitelist resmi sebagai satu-satunya rujukan legalitas.

**Bursa** (CFX, ICEX):[^5][^14]

- Menetapkan Daftar Aset Kripto yang dapat diperdagangkan — termasuk proses analisis, evaluasi berkala (setiap 3 bulan), dan publikasi daftar.
- Menetapkan peraturan dan tata tertib perdagangan yang mengikat PAKD.
- Mengawasi aktivitas perdagangan anggota dan memberikan sanksi.
- Melaporkan data transaksi agregat dan indikatif ke OJK.
- Memfasilitasi rekonsiliasi harian dengan lembaga kliring dan kustodian.

**Lembaga Kliring** (KKI, CACI):[^15][^21]

- Menjamin penyelesaian transaksi yang telah dicocokkan oleh bursa.
- Menyimpan dan mengelola dana fiat nasabah secara terpisah.
- Melakukan rekonsiliasi harian dengan bursa dan kustodian.
- Menangani situasi gagal bayar anggota, termasuk pencairan jaminan.
- Menetapkan persyaratan keanggotaan kliring bagi PAKD.

**Lembaga Kustodian** (ICC, Tennet, Arganis):[^19]

- Menyimpan aset kripto nasabah dengan standar keamanan yang ditentukan OJK (minimal 70% dalam *cold storage*).
- Memelihara dan mengawasi aset serta memastikan ketersediaan saat diperlukan.
- Menyerahkan aset berdasarkan instruksi yang sah dari PAKD atau nasabah.
- Melakukan rekonsiliasi harian dan melaporkan hasilnya ke OJK.
- Menerapkan teknologi keamanan yang setara dengan standar perbankan.

**PAKD**:[^24][^31]

- Menyediakan platform bagi nasabah untuk melakukan transaksi (bukan menyimpan aset).
- Menerapkan KYC dan program APU PPT.
- Menyampaikan laporan berkala (bulanan, triwulan, tahunan) ke OJK.
- Memastikan ketersediaan aset di kustodian sesuai dengan saldo nasabah yang tercatat.
- Tidak boleh menyimpan dana atau aset nasabah di luar mekanisme kliring dan kustodian.

**Auditor**:

- Melakukan audit tahunan terhadap laporan keuangan PAKD, bursa, kliring, dan kustodian.
- Memeriksa kecukupan sistem pengendalian internal, termasuk rekonsiliasi aset.
- Menyampaikan laporan audit ke OJK.

**Bank**:

- Menyediakan rekening terpisah untuk penitipan dana nasabah (*segregated account*) yang dapat dipantau oleh lembaga kliring.
- Menjadi mitra pembayaran untuk setoran dan penarikan dana nasabah.

## Implikasi untuk Tokenisasi Aset

**Persetujuan bursa sebagai pintu masuk.** Sebelum aset tokenisasi dapat diperdagangkan, bursa harus menyetujui dan memasukkan aset tersebut ke dalam Daftar Aset Kripto. Proses analisis bursa mencakup evaluasi terhadap aspek hukum, teknis, dan risiko dari aset yang diajukan. PAKD dapat mengusulkan penambahan aset, tetapi keputusan akhir berada di tangan bursa.[^5] Founder harus menyiapkan *whitepaper*, *legal opinion*, dan *audit kontrak pintar* sebagai dokumen pendukung pengajuan.

**Kustodi sebagai kewajiban.** Jika aset tokenisasi masuk dalam Daftar Aset Kripto, aset tersebut wajib disimpan di kustodian yang berizin. Implikasinya, kontrak pintar token harus mendukung mekanisme kustodi — termasuk kemampuan *freeze*, *recovery*, dan *multi-signature* yang kompatibel dengan sistem kustodian.[^19]

**Pilihan bursa sebagai strategi.** Dua bursa menawarkan pendekatan berbeda. ICEX secara eksplisit menargetkan tokenisasi RWA dan stablecoin — sehingga proses *listing* mungkin lebih cepat untuk aset yang sesuai dengan fokus tersebut.[^13] CFX memiliki basis anggota yang lebih besar dan pengalaman lebih lama dalam menangani berbagai jenis aset kripto. Founder perlu melakukan pendekatan ke kedua bursa untuk memahami persyaratan *listing* masing-masing.

**Kepastian institusional sebagai pembeda.** Arsitektur pasar Indonesia — dengan pemisahan fungsi yang ketat — memberikan kepastian hukum yang dibutuhkan oleh investor institusional. Dana pensiun, perusahaan asuransi, dan manajer investasi pada umumnya memiliki kebijakan internal yang melarang investasi pada aset digital tanpa pemisahan kustodi yang jelas. Struktur Indonesia memenuhi persyaratan tersebut. Bagi founder yang menargetkan pendanaan institusional, kejelasan infrastruktur ini adalah *selling point* yang harus dikomunikasikan secara eksplisit dalam *pitch deck* dan dokumen penawaran.

**Rekonsiliasi harian sebagai alat verifikasi.** Mekanisme rekonsiliasi harian antara bursa, kliring, dan kustodian menciptakan rantai verifikasi independen yang dapat diaudit oleh pihak ketiga. Untuk aset tokenisasi yang mewakili aset dunia nyata, mekanisme ini memungkinkan auditor untuk memverifikasi bahwa jumlah token yang beredar tidak melebihi nilai aset yang dijaminkan tanpa harus memeriksa sistem PAKD secara langsung. Cukup dengan membandingkan catatan bursa, kliring, dan kustodian.

**Bentuk partisipasi yang fleksibel.** Menjadi PAKD bukan satu-satunya jalur untuk menerbitkan aset tokenisasi. Founder dapat:

1. Menjadi PAKD — membutuhkan modal, sistem, dan proses perizinan yang lengkap.
2. Bekerja sama dengan PAKD yang sudah ada sebagai *issuer* — PAKD menjadi saluran distribusi dan kepatuhan.
3. Mengajukan izin sebagai "Pihak lain yang ditetapkan OJK" — jika model bisnis tokenisasi Anda tidak sepenuhnya cocok dengan kategori PAKD tradisional, POJK 27/2024 membuka kemungkinan ini.[^2]

Pilihan di atas harus didiskusikan dengan konsultan hukum yang berpengalaman dalam perizinan OJK sektor IAKD.

## Ringkasan

Infrastruktur pasar aset kripto Indonesia dibangun di atas prinsip pemisahan fungsi yang ketat antara bursa, kliring, dan kustodian — sebuah model yang dirancang untuk memberikan kepastian hukum bagi seluruh peserta pasar, terutama investor institusional. Bappebti meletakkan fondasi kelembagaan pada periode 2018–2025. OJK melanjutkan dan memperkuat kerangka tersebut dengan pendekatan regulasi yang setara dengan sektor jasa keuangan lainnya sejak Januari 2025.

Dengan dua bursa (CFX dan ICEX), dua lembaga kliring (KKI dan CACI), dan tiga kustodian (ICC, Tennet, Arganis), Indonesia telah memiliki infrastruktur yang cukup untuk mendukung pertumbuhan tokenisasi aset. Bagi seorang founder, pemahaman terhadap peran, hubungan, dan persyaratan perizinan dari setiap lembaga ini adalah prasyarat pertama — sebelum menulis kode, sebelum menerbitkan token, dan sebelum mengajukan izin ke OJK.

---

## Referensi

[^1]: Suara.com, "Memahami Arsitektur Pasar Kripto Indonesia: Antara Bursa Kripto CFX dan ICC", 6 Maret 2026. https://www.suara.com/bisnis/2026/03/06/061500/memahami-arsitektur-pasar-kripto-indonesia-antara-bursa-kripto-cfx-dan-icc

[^2]: OJK, "Peraturan Otoritas Jasa Keuangan Nomor 27 Tahun 2024 tentang Penyelenggaraan Perdagangan Aset Keuangan Digital Termasuk Aset Kripto (POJK AKD AK)". https://ojk.go.id/id/regulasi/Pages/POJK-27-2024-AKD-AK.aspx

[^3]: OJK, "Perubahan Atas Peraturan Otoritas Jasa Keuangan Nomor 27 Tahun 2024 — POJK 23/2025". https://ojk.go.id/id/regulasi/Pages/POJK-23-2025-Perubahan-POJK-27-Tahun-2024-tentang-Penyelenggaraan-Perdagangan-Aset-Keuangan-Digital-Termasuk-Aset-Kripto.aspx

[^4]: OJK, "Siaran Pers: OJK Terbitkan Whitelist Penyelenggara Perdagangan Aset Keuangan Digital dan Aset Kripto Berizin/Terdaftar", 19 Desember 2025. https://ojk.go.id/id/berita-dan-kegiatan/siaran-pers/Pages/OJK-Terbitkan-Whitelist-Penyelenggara-Perdagangan-Aset-Keuangan-Digital-Dan-Aset-Kripto-Berizin.aspx

[^5]: OJK, "FAQ POJK 27 Tahun 2024 tentang Penyelenggaraan Perdagangan Aset Keuangan Digital Termasuk Aset Kripto". https://ojk.go.id/id/regulasi/Documents/Pages/POJK-27-2024-AKD-AK/FAQ%20POJK%2027%202024%20Penyelenggaraan%20Perdagangan%20Aset%20Keuangan%20Digital%20Termasuk%20Aset%20Kripto.pdf

[^6]: OJK, "Siaran Pers: Bappebti Kemendag Alihkan Tugas Pengaturan dan Pengawasan Aset Keuangan Digital termasuk Aset Kripto serta Derivatif Keuangan kepada OJK dan BI", 10 Januari 2025. https://ojk.go.id/id/berita-dan-kegiatan/siaran-pers/Pages/Bappebti-Kemendag-Alihkan-Tugas-Aset-Keuangan-Digital-termasuk-Aset-Kripto-serta-Derivatif-Keuangan-kepada-OJK-dan-BI.aspx

[^7]: CFX, "Bursa Kripto Indonesia". https://www.cfx.co.id/id

[^8]: CFX, "CFX: Industri Aset Kripto Tetap Tumbuh di 2026, Didukung Adopsi Korporasi", 20 Januari 2026. https://www.cfx.co.id/id/news/cfx-industri-aset-kripto-tetap-tumbuh-di-2026-didukung-adopsi-korporasi

[^9]: CFX, "Bursa CFX Dukung Pertumbuhan Industri Aset Kripto yang Berkelanjutan", 21 Juli 2025. https://www.cfx.co.id/id/news/bursa-cfx-dukung-pertumbuhan-industri-aset-kripto-yang-berkelanjutan

[^10]: CFX, "Daftar 22 Anggota Bursa CFX yang Berizin sebagai PAKD", 9 Juni 2026. https://www.cfx.co.id/id/news/daftar-22-anggota-bursa-cfx-yang-berizin-sebagai-pakd-1

[^11]: CFX, "Sinergi Pemangku Kepentingan di CFX Crypto Conference 2026", 9 Juni 2026. https://www.cfx.co.id/id/news/sinergi-pemangku-kepentingan-di-cfx-crypto-conference-2026-dorong-inovasi-industri-aset-kripto-kripto-lokal-dan-mendorong-regulasi-adaptif

[^12]: CNBC Indonesia, "OJK Buka Suara Soal Pendirian Bursa Kripto Baru ICEX", 8 Januari 2026. https://www.cnbcindonesia.com/market/20260108092526-17-700552/ojk-buka-suara-soal-pendirian-bursa-kripto-baru-icex

[^13]: Kompas.com, "ICEx Resmi Jadi SRO Kripto Berizin OJK, Dorong Tata Kelola Pasar Digital", 12 Januari 2026. https://money.kompas.com/read/2026/01/12/103339426/icex-resmi-jadi-sro-kripto-berizin-ojk-dorong-tata-kelola-pasar-digital

[^14]: ICEX, "Indonesia Crypto Exchange Launches as Institutional Crypto Market Infrastructure in Southeast Asia", 2 April 2026. https://icex.id/indonesia-crypto-exchange-launches-as-institutional-crypto-market-infrastructure-in-southeast-asia/

[^15]: PT Kliring Komoditi Indonesia. https://www.kliringkomoditi.id/id/

[^16]: Bappebti, "Siaran Pers: Bappebti Tetapkan Bursa, Kliring, dan Pengelola Tempat Penyimpanan Aset Kripto", 20 Juli 2023. https://bappebti.go.id/resources/docs/siaran_pers_2023_07_20_isa2gi7k_id.pdf

[^17]: Liputan6.com, "PT KBI Ditunjuk Jadi Kliring Berjangka Perdagangan Fisik Aset Kripto", 28 Desember 2023. https://www.liputan6.com/crypto/read/5492794/pt-kbi-ditunjuk-jadi-kliring-berjangka-perdagangan-fisik-aset-kripto

[^18]: ICC (Indonesia Coin Custodian). https://www.coincustodian.id/id

[^19]: ICC, "ICC: Lembaga Kustodian Pertama Berizin OJK, Jamin Keamanan Aset Kripto Konsumen", 26 Desember 2025. https://www.coincustodian.id/id/publications/siaran-pers/icc-lembaga-kustodian-pertama-berizin-ojk-jamin-keamanan-aset-kripto-konsumen

[^20]: OJK, "Pengumuman Pemberian Izin Usaha Pengelola Tempat Penyimpanan Aset Keuangan Digital kepada PT Arganis Konsultindo Utama", 3 Maret 2026. https://ojk.go.id/id/berita-dan-kegiatan/pengumuman/Documents/PENG-4.IK.01.2026_Pemberian%20Izin%20Usaha%20PT%20Arganis%20Konsultindo%20Utama.pdf

[^21]: OJK, "Pengumuman Pemberian Izin Usaha Lembaga Kliring — PT Pranata Karya Solusi", 5 Maret 2026. https://ojk.go.id/id/berita-dan-kegiatan/pengumuman/Pages/Pemberian-Izin-Usaha-PT-Pranata-Karya-Solusi.aspx

[^22]: Pintu Academy, "Panduan Lengkap Regulasi Aset Crypto di Indonesia 2026", 14 Juli 2026. https://pintu.co.id/academy/post/panduan-lengkap-regulasi-aset-crypto-di-indonesia-2026

[^23]: Neraca.co.id, "Kliring Komoditi dan Kustodian Koin Dapat Izin dari Bappebti", Januari 2024. https://www.neraca.co.id/article/193134/kliring-komoditi-dan-kustodian-koin-dapat-izin-dari-bappebti

[^24]: Tokocrypto News, "Dana Nasabah Crypto Disimpan di Mana? Skema Penyimpanan di Exchange Lokal", 5 Januari 2026. https://news.tokocrypto.com/dana-nasabah-crypto-disimpan-di-mana/

[^25]: Indodax Academy, "Begini Skema Penyimpanan Dana Nasabah Kripto di Exchange Lokal", 7 Januari 2026. https://indodax.com/academy/penyimpanan-dana-nasabah-kripto-lokal/

[^26]: OJK, "SEOJK Nomor 34/SEOJK.07/2025 tentang Rencana Bisnis Penyelenggara Perdagangan Aset Keuangan Digital". https://ojk.go.id/id/regulasi/Pages/SEOJK-Nomor-34-SEOJK07-2025-Rencana-Bisnis-Penyelenggara-Perdagangan-Aset-Keuangan-Digital.aspx

[^27]: OJK, "Siaran Pers: POJK Nomor 16 Tahun 2025 tentang Penilaian Kemampuan dan Kepatutan Sektor IAKD", 22 Juli 2025. https://ojk.go.id/id/berita-dan-kegiatan/siaran-pers/Pages/POJK-16-Tahun-2025-PKK-PKPU-IAKD.aspx

[^28]: Bisnis.com, "Daftar Pedagang Aset Kripto dan Kustodian Resmi OJK Terbaru", 19 Desember 2025. https://market.bisnis.com/read/20251219/94/1938265/daftar-pedagang-aset-kripto-dan-kustodian-resmi-ojk-terbaru

[^29]: Kompas.com, "OJK Siapkan Aturan soal Transisi Pengawasan Aset Kripto", 2 Januari 2025. https://money.kompas.com/read/2025/01/02/144200226/ojk-siapkan-aturan-soal-transisi-pengawasan-aset-kripto

[^30]: BCA Sekuritas, "ICEx Resmi Beroperasi sebagai Infrastruktur Kripto Terintegrasi", 2 April 2026. https://bcasekuritas.co.id/latest-news/news/icex-resmi-beroperasi-sebagai-infrastruktur-kripto-terintegrasi

[^31]: ItWorks, "Diawasi OJK, Industri Aset Kripto Kini Diklaim Lebih Aman", 6 Januari 2026. https://www.itworks.id/79020/diawasi-ojk-industri-aset-kripto-kini-diklaim-lebih-aman.html

[^32]: KKI, "Daftar Whitelist Penyelenggara Perdagangan Aset Keuangan Digital dan Aset Kripto Berizin OJK", 24 Desember 2025. https://www.kliringkomoditi.id/daftar-whitelist-penyelenggara-perdagangan-aset-keuangan-digital-dan-aset-kripto-berizin-ojk/

[^33]: OJK, "SEOJK Nomor 16/SEOJK.07/2025 tentang Penerapan Program APU PPT PPPSPM bagi Pedagang Aset Keuangan Digital". https://ojk.go.id/id/regulasi/Pages/SEOJK-16-SEOJK07-2025-Penerapan-Program-APU-PPT-dan-Pencegahan-Pendanaan-Proliferasi-Senjata-Pemusnah-Massal-Pedagang-AKD.aspx
