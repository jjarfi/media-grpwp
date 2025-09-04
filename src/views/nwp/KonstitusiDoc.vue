<script setup>
import { ref } from 'vue';

const currentStep = ref('0'); // default ke Mukadimah

// fungsi ubah angka ke romawi
const toRoman = (num) => {
    const romans = [
        ['M', 'CM', 'D', 'CD', 'C', 'XC', 'L', 'XL', 'X', 'IX', 'V', 'IV', 'I'],
        [1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1]
    ];
    let result = '';
    for (let i = 0; i < romans[0].length; i++) {
        while (num >= romans[1][i]) {
            result += romans[0][i];
            num -= romans[1][i];
        }
    }
    return result;
};
</script>

<template>
    <div class="card p-4">
        <Stepper v-model="currentStep">
            <!-- Daftar isi scrollable -->
            <div class="overflow-x-auto">
                <StepList class="whitespace-nowrap">
                    <Step value="0">Mukadimah</Step>
                    <Step v-for="n in 21" :key="n" :value="n.toString()"> BAB {{ toRoman(n) }} </Step>
                </StepList>
            </div>

            <StepPanels>
                <!-- Panel Mukadimah -->
                <StepPanel value="0" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">MUKADIMAH</h2>
                        <p>
                            Kami mengaku dengan penuh syukur dan pujian bahwa bangsa dan negara West Papua adalah dibawah kuasa kemuliaan dan kebenaran Yahweh, yang menciptakan Alam semesta, Leluhur dan segala berkat yang dilimpahkan bagi bangsa
                            Papua.
                        </p>
                        <p>Perjuangan bangsa Papua bersama segenap makhluk di Tanah Papua untuk hidup bebas, merdeka, berdaulat, damai dan harmonis di atas tanah leluhurnya adalah Hak Asasi yang tidak dapat diganggu-gugat.</p>
                        <p>
                            Sebab perjuangan untuk mencapai kebebasan, kemerdekaan, kedaulatan, kedamaian dan keharmonisan hidup di West Papua telah ditandai Kongres Rakyat Papua I – Manifesto Politik 19 Oktober 1961, kemudian dilanjutkan dengan
                            pengibaran bendera Bintang Fajar pada 1 Desember 1961, pendirian Organisasi Papua Merdeka 14 April 1963, Proklamasi Pemerintahan Revolusioner Sementara 1 Juli 1971, Proklamasi Negara Republik Melanesia Barat 14 Desember
                            1988, Proklamasi Negara Papua New Guinea Barat 27 November 1997, Kongres Rakyat Papua II 4 Juni 2000, Deklarasi West Papua National Authority 16 Agustus 2004, Deklarasi Pembentukan West Papua National Coalition for
                            Liberation 1 Desember 2005, Deklarasi Yeondowa 1 Juli 2006, Kongres Rakyat Papua III – Deklarasi Negara Federal Republik Papua Barat 19 Oktober 2011, Deklarasi Parlemen Nasional West Papua 9 April 2012 hingga Deklarasi
                            Saralana 6 Desember 2014 merupakan wujud upaya bangsa Papua secara kolektif dalam rangka membela dan mempertahankan jatidiri, harkat dan martabat serta menentang segala jenis dan bentuk penjajahan demi menjamin pulau New
                            Guinea bagi keselamatan hidup planet bumi.
                        </p>
                        <p>Maka disusunlah Konstitusi Pemerintah Sementara United Liberation Movement for West Papua sebagai landasan hukum dan politik dalam mencapai tujuan pembebasan.</p>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('1')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB I -->
                <StepPanel value="1" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB I</h2>
                        <h3 class="text-lg font-semibold text-center">NAMA, BENTUK DAN KEDAULATAN</h3>

                        <p>
                            <strong>Pasal 1</strong><br />
                            Pemerintah United Liberation Movement for West Papua, selanjutnya disebut Pemerintah Sementara.
                        </p>

                        <p>
                            <strong>Pasal 2</strong><br />
                            Pemerintah Sementara berbentuk Persatuan.
                        </p>

                        <p>
                            <strong>Pasal 3</strong><br />
                            Kedaulatan sepenuhnya berada di tangan rakyat dan dijalankan oleh Pemerintah Sementara.
                        </p>

                        <p>
                            <strong>Pasal 4</strong><br />
                            Pemerintahan Sementara dijalankan berdasarkan Konstitusi.
                        </p>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('0')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('2')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB II -->
                <StepPanel value="2" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB II<br />KONGRES</h2>

                        <div>
                            <p class="font-semibold">Pasal 5</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Kongres adalah badan tertinggi Pemerintahan Sementara.</li>
                                <li>Kongres terdiri dari Legislative Council dan Senat.</li>
                                <li>Senat terdiri dari utusan wilayah adat, utusan agama, utusan perempuan, kalangan profesional dan kelompok pendukung yang disetujui oleh Legislative Council.</li>
                                <li>Kongres bersidang sedikitnya sekali dalam 5 tahun.</li>
                                <li>Bila dipandang perlu, sewaktu-waktu dapat dilakukan Kongres Luar Biasa.</li>
                                <li>Kongres dan Kongres Luar Biasa memiliki kedudukan yang setara.</li>
                                <li>Kongres berwenang menetapkan, mengesahkan dan mengubah Konstitusi.</li>
                                <li>Kongres berwenang mengangkat dan memberhentikan Presiden dan Perdana Menteri.</li>
                                <li>Kongres berwenang meminta pertanggungjawaban Pemerintah Sementara.</li>
                                <li>Kongres berhak menerima atau menolak pertanggungjawaban Pemerintah Sementara.</li>
                                <li>Kongres berwenang menetapkan garis-garis besar haluan kebijakan Pemerintah Sementara.</li>
                                <li>Hal-hal lain menyangkut Kongres diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('1')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('3')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB III -->
                <StepPanel value="3" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB III<br />PEMERINTAH DAN KEKUASAAN</h2>

                        <div>
                            <p class="font-semibold">Pasal 6</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Pemerintah Sementara adalah pelaksana mandat kedaulatan rakyat.</li>
                                <li>Pemerintah Sementara menganut prinsip <i>trias politica</i>.</li>
                                <li>Pemerintah Sementara terdiri dari Legislative Council, Executive Council dan Judicative Council.</li>
                                <li>Pemerintah Sementara menjalankan sistem kepemimpinan bergilir.</li>
                                <li>Hal-hal lain menyangkut Pemerintah Sementara diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('2')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('4')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB IV -->
                <StepPanel value="4" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB IV<br />BADAN KONSTITUANTE</h2>

                        <div>
                            <p class="font-semibold">Pasal 7</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Badan Konstituante adalah badan yang dibentuk oleh Kongres.</li>
                                <li>Badan Konstituante bertugas membentuk Konstitusi Negara.</li>
                                <li>Badan Konstituante terdiri dari utusan Fraksi, unsur Adat, Akademisi dan Profesional.</li>
                                <li>Badan Konstituante bersifat Ad-Hoc.</li>
                                <li>Hal-hal lain menyangkut Badan Konstituante diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('3')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('5')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB V -->
                <StepPanel value="5" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB V<br />DEWAN PENASEHAT AGUNG</h2>

                        <div>
                            <p class="font-semibold">Pasal 8</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Dewan Penasehat Agung adalah badan yang dibentuk oleh Kongres.</li>
                                <li>Dewan Penasehat Agung bertugas memberikan penilaian, nasehat, arahan dan kritik serta memediasi berbagai pihak demi kepentingan kemajuan perjuangan pembebasan.</li>
                                <li>Dewan Penasehat Agung terdiri dari unsur Adat, Agama, Pertahanan dan Keamanan, profesi dan penasehat luar biasa yang disetujui oleh Fraksi.</li>
                                <li>Hasil Keputusan Dewan Penasehat Agung segera ditanggapi dan ditindaklanjuti oleh Pemerintah Sementara.</li>
                                <li>Dewan Penasehat Agung bersifat Ad-Hoc.</li>
                                <li>Hal-hal lain menyangkut Dewan Penasehat Agung diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('4')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('6')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB VI -->
                <StepPanel value="6" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB VI<br />BADAN PERTAHANAN DAN KEAMANAN</h2>

                        <div>
                            <p class="font-semibold">Pasal 9</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Badan Pertahanan dan Keamanan dibentuk oleh Kongres.</li>
                                <li>Badan Pertahanan dan Keamanan bertugas untuk urusan pertahanan dan keamanan.</li>
                                <li>Sistem Pertahanan dijalankan oleh West Papua Army.</li>
                                <li>Sistem Keamanan dijalankan oleh West Papua Police.</li>
                                <li>West Papua Army terdiri dari Tentara Pembebasan Nasional Organisasi Papua Merdeka, Tentara Pembebasan Nasional Papua Barat, Tentara Nasional Papua Barat dan Tentara Revolusi West Papua.</li>
                                <li>West Papua Police terdiri dari Satuan Tugas Papua, Satuan Tugas Koteka, Satuan Tugas Penjaga Tanah Papua, Kepolisian Federal Papua Barat dan satuan tugas lainnya.</li>
                                <li>Badan Pertahanan dan Keamanan membentuk West Papua Intelijen Services.</li>
                                <li>Badan Pertahanan dan Keamanan bersifat Ad-Hoc.</li>
                                <li>Hal-hal lain menyangkut Badan Pertahanan dan Keamanan diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('5')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('7')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB VII -->
                <StepPanel value="7" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB VII<br />LEGISLATIVE COUNCIL</h2>

                        <div>
                            <p class="font-semibold">Pasal 10</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Legislative Council dibentuk oleh Kongres.</li>
                                <li>Legislative Council bertugas untuk menjalankan fungsi perundang-undangan, fungsi anggaran dan fungsi pengawasan.</li>
                                <li>Legislative Council berjumlah lima belas orang utusan dari masing-masing Fraksi.</li>
                                <li>Legislative Council terdiri dari ketua, wakil ketua dan anggota yang dipilih melalui rapat paripurna Legislative Council.</li>
                                <li>Legislative Council berwenang membentuk peraturan perundang-undangan.</li>
                                <li>Legislative Council berwenang menetapkan anggaran pendapatan dan belanja Pemerintah Sementara.</li>
                                <li>Legislative Council memiliki hak prerogatif atau hak istimewa, hak inisiatif, hak angket dan hak interpelasi.</li>
                                <li>Legislative Council membentuk Fraksi dan komisi.</li>
                                <li>Legislative Council bersidang sekurang-kurangnya satu kali dalam setahun.</li>
                                <li>Masa jabatan anggota Legislative Council ialah lima tahun dan dapat dipilih kembali.</li>
                                <li>Hal-hal lain menyangkut Legislative Council diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('6')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('8')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB VIII -->
                <StepPanel value="8" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB VIII<br />EXECUTIVE COUNCIL</h2>

                        <div>
                            <p class="font-semibold">Pasal 11</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Executive Council dibentuk oleh Kongres.</li>
                                <li>Executive Council bertugas melaksanakan Undang-Undang dan anggaran.</li>
                                <li>Executive Council mewujudkan agenda perjuangan hak penentuan nasib sendiri untuk kemerdekaan dan kedaulatan politik dan hukum bangsa Papua.</li>
                                <li>Executive Council dipimpin oleh Presiden dan Perdana Menteri.</li>
                                <li>Presiden dan Perdana Menteri dipilih, diangkat dan diberhentikan oleh Kongres.</li>
                                <li>Presiden adalah kepala Pemerintah Sementara.</li>
                                <li>Perdana Menteri adalah Pelaksana Pemerintah Sementara.</li>
                                <li>Presiden dan Perdana Menteri berwenang membentuk kabinet.</li>
                                <li>Executive Council berwenang mengajukan rancangan peraturan perundang-undangan.</li>
                                <li>Executive Council berwenang mengajukan rancangan anggaran pendapatan dan belanja.</li>
                                <li>Presiden memiliki hak inisiatif dan hak prerogatif.</li>
                                <li>Perdana Menteri memiliki hak inisiatif.</li>
                                <li>Rapat Executive Council sekurang-kurangnya dilaksanakan satu kali dalam setahun.</li>
                                <li>Masa jabatan Presiden dan Perdana Menteri adalah lima tahun dan dapat dipilih kembali.</li>
                                <li>Hal-hal lain menyangkut Executive Council diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('7')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('9')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB IX -->
                <StepPanel value="9" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB IX<br />JUDICATIVE COUNCIL</h2>

                        <div>
                            <p class="font-semibold">Pasal 12</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Judicative Council dibentuk oleh Kongres.</li>
                                <li>Judicative Council bertugas untuk menjalankan fungsi pengawasan perundang-undangan dan fungsi Yudisial.</li>
                                <li>Judicative Council terdiri dari ketua, wakil ketua dan anggota.</li>
                                <li>Judicative Council diangkat dan dipilih oleh Pemerintah Sementara.</li>
                                <li>Judicative Council memiliki kewenangan peradilan.</li>
                                <li>Judicative Council bersifat independen dan tidak dapat diintervensi.</li>
                                <li>Judicative Council memiliki hak uji materi dan formil.</li>
                                <li>Judicative Council berwenang membentuk komisi Yudisial.</li>
                                <li>Rapat Judicative Council sekurang-kurangnya dilaksanakan satu kali dalam setahun.</li>
                                <li>Masa jabatan Judicative Council adalah lima tahun dan dapat dipilih kembali.</li>
                                <li>Hal-hal lain menyangkut Judicative Council diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('8')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('10')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB X -->
                <StepPanel value="10" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB X<br />NEGARA</h2>

                        <div>
                            <p class="font-semibold">Pasal 13</p>
                            <p>Negara yang diperjuangkan adalah West Papua:</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Secara geografis ialah bagian barat pulau New Guinea, terletak pada 129° BT – 141° BT dan 1° LU – 10° LS.</li>
                                <li>
                                    Secara politik di bagian timur berbatasan dengan negara Papua New Guinea, bagian utara berbatasan dengan Samudera Pasifik, bagian selatan berbatasan dengan negara Australia dan bagian barat berbatasan dengan negara
                                    Indonesia.
                                </li>
                                <li>Secara historis adalah bekas Nederlands-Nieuw-Guinea, Provinsi Irian Barat, Provinsi Irian Jaya, Provinsi Papua dan Provinsi Papua Barat.</li>
                                <li>Hal-hal lain menyangkut Wilayah diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('9')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('11')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB XI -->
                <StepPanel value="11" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB XI<br />PENDUDUK, WARGA NEGARA DAN KEBANGSAAN</h2>

                        <div>
                            <p class="font-semibold">Pasal 14</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Penduduk ialah seluruh Komunitas Makhluk yang berdomisili di West Papua dan disahkan dengan Konstitusi Pemerintah Sementara.</li>
                                <li>Warga Negara ialah orang-per orang ras Melanesia yang secara genetik berasal dari West Papua dan Non Melanesia yang berkeinginan menjadi warga Negara dan disahkan dengan Konstitusi Pemerintah Sementara.</li>
                                <li>Bangsa Papua ialah orang-per orang ras Melanesia secara genetik berasal dari West Papua yang berdomisili di West Papua dan di luar West Papua.</li>
                                <li>Penduduk bangsa Papua yang berdomisili di West Papua dan di pengasingan berhak atas status kewarganegaraan.</li>
                                <li>Hal-hal lain menyangkut Penduduk, Warga Negara dan Kebangsaan diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('10')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('12')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB XII -->
                <StepPanel value="12" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB XII<br />SIMBOL-SIMBOL</h2>

                        <div>
                            <p class="font-semibold">Pasal 15</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Bendera adalah Bintang Fajar.</li>
                                <li>Lambang adalah Burung Mambruk.</li>
                                <li>Lagu adalah Hai Tanah Ku Papua.</li>
                                <li>Semboyan adalah One People One Soul.</li>
                                <li>Hal-hal lain menyangkut simbol-simbol diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('11')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('13')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB XIII -->
                <StepPanel value="13" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB XIII<br />BAHASA</h2>

                        <div>
                            <p class="font-semibold">Pasal 16</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Bahasa bangsa adalah Bahasa Melanesia terdiri dari bahasa suku bangsa di West Papua.</li>
                                <li>Bahasa persatuan adalah Tok Pisin, Bahasa Inggris dan Melayu-Papua.</li>
                                <li>Hal-hal lain menyangkut bahasa diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('12')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('14')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB XIV -->
                <StepPanel value="14" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB XIV<br />WILAYAH PEMERINTAHAN</h2>

                        <div>
                            <p class="font-semibold">Pasal 17</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Pemerintah Sementara berkedudukan di West Papua.</li>
                                <li>Kantor pusat Pemerintah Sementara bertempat di Port Vila, Negara Republik Vanuatu.</li>
                                <li>Kantor Pemerintah Sementara di West Papua berkedudukan di Wamena.</li>
                                <li>Wilayah kerja Pemerintah Sementara terdiri dari Pemerintah Sementara Wilayah dan Pemerintah Sementara Daerah.</li>
                                <li>Wilayah kerja dibagi berdasarkan wilayah adat.</li>
                                <li>Pemerintah Sementara wilayah dipimpin oleh Kepala Eksekutif Wilayah.</li>
                                <li>Pemerintah Sementara daerah dipimpin oleh Kepala Eksekutif Daerah.</li>
                                <li>Pembentukan Pemerintah Sementara wilayah dan Pemerintah Sementara daerah ditetapkan oleh Kongres.</li>
                                <li>Kepala Eksekutif Wilayah dan Kepala Eksekutif Daerah diangkat dan diberhentikan oleh Executive Council dengan persetujuan Legislative Council.</li>
                                <li>Pemerintah Sementara sebagaimana termaktub pada Pasal 6 berlaku di tingkat wilayah dan daerah.</li>
                                <li>Hal-hal lain menyangkut Wilayah Pemerintahan diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('13')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('15')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB XV -->
                <StepPanel value="15" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-4">
                        <h2 class="text-xl font-bold text-center">BAB XV<br />PENGAMBILAN KEPUTUSAN</h2>

                        <div>
                            <p class="font-semibold">Pasal 18</p>
                            <p>Pengambilan keputusan terdiri atas Kongres, Sidang dan Rapat.</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Kongres ialah forum pengambilan keputusan tertinggi.</li>
                                <li>Kongres dinyatakan sah apabila dihadiri oleh dua pertiga anggota Kongres.</li>
                                <li>Keputusan Kongres dinyatakan sah apabila memperoleh dukungan suara dua pertiga dari peserta kongres.</li>
                                <li>Keputusan Kongres dicapai melalui konsensus dan atau pemungutan suara.</li>
                                <li>Sidang terdiri dari Sidang Istimewa, Sidang Paripurna, Sidang Tahunan.</li>
                                <li>Sidang dinyatakan sah apabila dihadiri oleh dua pertiga peserta sidang.</li>
                                <li>Keputusan Sidang dinyatakan sah apabila memperoleh dukungan suara dua pertiga peserta sidang.</li>
                                <li>Keputusan Sidang dicapai melalui konsensus dan atau pemungutan suara.</li>
                                <li>Rapat-rapat ialah Rapat Legislative Council, Rapat Executive Council, Rapat Judicative Council, Rapat Badan Konstituante, Rapat Badan Pertahanan dan Keamanan dan Rapat Dewan Penasehat Agung.</li>
                                <li>Rapat-rapat terdiri dari rapat koordinasi dan rapat kerja.</li>
                                <li>Tata cara Kongres, Sidang dan Rapat diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('14')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('16')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB XVI -->
                <StepPanel value="16" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-6">
                        <h2 class="text-xl font-bold text-center">BAB XVI<br />HAK-HAK DASAR</h2>

                        <!-- Pasal 19 -->
                        <div>
                            <p class="font-semibold">Pasal 19<br />Hak Hidup</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Setiap mahkluk secara individu dan kolektif memiliki hak asasi untuk hidup harmonis.</li>
                                <li>Setiap mahkluk secara individu dan kolektif memiliki hak atas harkat dan martabat.</li>
                                <li>Pemerintah Sementara mengakui dan menjamin hak hidup setiap mahkluk secara individu dan kolektif.</li>
                                <li>Hal-hal lain menyangkut Hak Hidup diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 20 -->
                        <div>
                            <p class="font-semibold">Pasal 20<br />Hak Keamanan</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Orang perorangan dan kolektif berhak bebas dari rasa takut.</li>
                                <li>Orang perorangan dan kolektif berhak atas keamanan.</li>
                                <li>Orang perorangan dan kolektif berhak atas hidup damai secara lahir dan batin.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui hak keamanan orang perorangan dan kolektif.</li>
                                <li>Hal-hal lain menyangkut Hak Keamanan diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 21 -->
                        <div>
                            <p class="font-semibold">Pasal 21<br />Hak Kebebasan</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Orang perorangan dan kolektif memiliki hak atas kebebasan berkumpul, berserikat dan menyatakan pendapat.</li>
                                <li>Orang perorangan dan kolektif memiliki hak bergerak dan bertempat tinggal.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui hak kebebasan orang perorangan dan kolektif.</li>
                                <li>Hal-hal lain menyangkut Hak Kebebasan diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 22 -->
                        <div>
                            <p class="font-semibold">Pasal 22<br />Hak Kepemilikan</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Orang perorangan dan kolektif berhak atas kepemilikan.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui hak atas kepemilikan orang perorangan dan kolektif.</li>
                                <li>Hal-hal lain menyangkut Hak Kepemilikan diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 23 -->
                        <div>
                            <p class="font-semibold">Pasal 23<br />Hak Sosial</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Orang perorangan dan kolektif berhak atas jaminan sosial.</li>
                                <li>Orang perorangan berhak membentuk rumah tangga.</li>
                                <li>Laki-laki dan Perempuan memiliki hak yang sama di hadapan hukum.</li>
                                <li>Hal-hal lain menyangkut Hak Sosial diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 24 -->
                        <div>
                            <p class="font-semibold">Pasal 24<br />Hak Politik</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Orang perorangan dan kolektif memiliki hak politik.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui hak Politik.</li>
                                <li>Hal-hal lain menyangkut Hak Politik diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 25 -->
                        <div>
                            <p class="font-semibold">Pasal 25<br />Hak Ekonomi</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Orang perorangan dan kolektif berhak untuk hidup berkecukupan.</li>
                                <li>Orang perorangan dan kolektif berhak mengelola sumber-sumber ekonomi.</li>
                                <li>Pemerintah Sementara mengakui dan menjamin pengelolaan sumber-sumber ekonomi untuk kehidupan yang berkecukupan.</li>
                                <li>Hal-hal lain menyangkut Hak Ekonomi diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 26 -->
                        <div>
                            <p class="font-semibold">Pasal 26<br />Hak Kesehatan</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Orang perorangan dan kolektif memiliki hak atas kesehatan.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui hak atas kesehatan.</li>
                                <li>Hal-hal lain menyangkut Hak Kesehatan diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 27 -->
                        <div>
                            <p class="font-semibold">Pasal 27<br />Hak Pendidikan</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Orang perorangan dan kolektif memiliki hak atas pendidikan dan intelektualitas.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui hak atas pendidikan dan intelektualitas.</li>
                                <li>Hal-hal lain menyangkut Hak Pendidikan diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 28 -->
                        <div>
                            <p class="font-semibold">Pasal 28<br />Hak Budaya</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Orang perorangan dan kolektif memiliki hak adat istiadat dan budaya.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui hak adat istiadat dan budaya.</li>
                                <li>Hak adat istiadat dan budaya tidak dapat digadaikan dan disalahgunakan.</li>
                                <li>Hal-hal lain menyangkut Hak Budaya diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 29 -->
                        <div>
                            <p class="font-semibold">Pasal 29<br />Hak Lingkungan Hidup</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Orang perorangan dan kolektif memiliki hak atas lingkungan hidup yang sehat.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui hak atas lingkungan hidup yang sehat.</li>
                                <li>Orang perorangan, kolektif dan Pemerintah Sementara menjamin lingkungan sebagai sumber kehidupan planet bumi.</li>
                                <li>Hal-hal lain menyangkut Hak Lingkungan Hidup diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 30 -->
                        <div>
                            <p class="font-semibold">Pasal 30<br />Hak Keyakinan dan Agama</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Orang perorangan dan kolektif memiliki hak atas keyakinan dan agama.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui hak atas keyakinan dan agama.</li>
                                <li>Hal-hal lain menyangkut Hak Keyakinan dan Agama diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 31 -->
                        <div>
                            <p class="font-semibold">Pasal 31<br />Hak Tanah, Air dan Udara</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Orang perorangan dan kolektif memiliki hak atas tanah, air dan udara.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui hak atas tanah, air dan udara.</li>
                                <li>Tanah, air dan udara tidak diperjualbelikan.</li>
                                <li>Hal-hal lain menyangkut Hak Tanah, Air dan Udara diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 32 -->
                        <div>
                            <p class="font-semibold">Pasal 32<br />Hak Tanda Jasa</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Orang perorangan dan kolektif memiliki hak atas penghargaan, tanda jasa dan pahlawan perjuangan kemerdekaan West Papua.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui hak atas penghargaan dan tanda jasa.</li>
                                <li>Hal-hal lain menyangkut Hak Tanda Jasa diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('15')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('17')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB XVII -->
                <StepPanel value="17" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-6">
                        <h2 class="text-xl font-bold text-center">BAB XVII<br />KEKAYAAN</h2>

                        <!-- Pasal 33 -->
                        <div>
                            <p class="font-semibold">Pasal 33</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Kekayaan terdiri dari sumber daya alam, sumber daya manusia dan sumber daya keuangan.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui kekayaan sumber daya alam, sumber daya manusia dan sumber daya keuangan.</li>
                                <li>Kekayaan dipergunakan untuk kepentingan perjuangan pembebasan.</li>
                                <li>Hal-hal lain menyangkut Kekayaan diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 34 -->
                        <div>
                            <p class="font-semibold">Pasal 34<br /><span class="italic">Sumber Daya Alam</span></p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Sumber daya alam terdiri dari energi, mineral, hewan dan tumbuh-tumbuhan.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui sumber daya alam.</li>
                                <li>Hal-hal lain menyangkut Sumber Daya Alam diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 35 -->
                        <div>
                            <p class="font-semibold">Pasal 35<br /><span class="italic">Sumber Daya Manusia</span></p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Sumber daya manusia terdiri dari jasa, keterampilan, profesionalisme, keahlian dan intelektualitas.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui sumber daya manusia.</li>
                                <li>Hal-hal lain menyangkut sumber daya manusia diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>

                        <!-- Pasal 36 -->
                        <div>
                            <p class="font-semibold">Pasal 36<br /><span class="italic">Sumber Daya Keuangan</span></p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Sumber daya keuangan terdiri dari sumbangan rakyat, pajak, BEA, hasil usaha, donor, hibah dan pinjaman.</li>
                                <li>Pemerintah Sementara menjamin dan mengakui sumber daya keuangan.</li>
                                <li>Executive Council berwenang mengelola sumber daya keuangan.</li>
                                <li>Hal-hal lain menyangkut sumber daya keuangan diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('16')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('18')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB XVIII -->
                <StepPanel value="18" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-6">
                        <h2 class="text-xl font-bold text-center">BAB XVIII<br />KERJA SAMA</h2>

                        <!-- Pasal 37 -->
                        <div>
                            <p class="font-semibold">Pasal 37</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Pemerintah Sementara menjalin kerja sama dengan lembaga pemerintah dan lembaga non pemerintah.</li>
                                <li>Bentuk kerja sama lembaga pemerintah terdiri dari bilateral, multilateral, sub regional, regional, interregional, internasional dan global.</li>
                                <li>Bentuk kerja sama non pemerintah terdiri dari kerja sama perdagangan dan investasi, riset dan teknologi, kebudayaan dan olahraga, keagamaan dan advokasi.</li>
                                <li>Hal-hal lain menyangkut Kerja Sama diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('17')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('19')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB XIX -->
                <StepPanel value="19" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-6">
                        <h2 class="text-xl font-bold text-center">BAB XIX<br />PELANGGARAN DAN SANKSI</h2>

                        <!-- Pasal 38 -->
                        <div>
                            <p class="font-semibold">Pasal 38</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Pemerintah Sementara wajib tunduk dan melaksanakan ketentuan Konstitusi.</li>
                                <li>Pelanggaran dan penyimpangan terhadap Konstitusi wajib dikenakan sanksi.</li>
                                <li>Pelanggaran dan sanksi terdiri dari tindakan yang menyimpang Konstitusi.</li>
                                <li>Sanksi diberlakukan kepada orang perorangan dan atau kolektif.</li>
                                <li>Judicative Council berwenang memberikan sanksi.</li>
                                <li>Hal-hal lain menyangkut Pelanggaran dan Sanksi diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('18')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('20')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB XX -->
                <StepPanel value="20" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-6">
                        <h2 class="text-xl font-bold text-center">BAB XX<br />PERUBAHAN KONSTITUSI</h2>

                        <!-- Pasal 39 -->
                        <div>
                            <p class="font-semibold">Pasal 39</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Perubahan Konstitusi dilakukan dalam Kongres dan atau Kongres Luar Biasa.</li>
                                <li>Perubahan Konstitusi sebagaimana termaktub pada ayat 1 di atas, dilakukan sekurang-kurangnya oleh dua per tiga dari jumlah anggota Kongres.</li>
                                <li>Hal-hal yang menyangkut hajat hidup orang banyak dilakukan jajak pendapat rakyat.</li>
                                <li>Hal-hal lain menyangkut Perubahan Konstitusi diatur lebih lanjut dalam Undang-Undang.</li>
                            </ol>
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('19')" />
                        <div class="flex-auto"></div>
                        <Button label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback('21')" />
                    </div>
                </StepPanel>
                <!-- Panel BAB XXI -->
                <StepPanel value="21" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-full overflow-y-auto p-4 text-justify space-y-8">
                        <h2 class="text-xl font-bold text-center">BAB XXI<br />ATURAN PERALIHAN DAN PENUTUP</h2>

                        <!-- Aturan Peralihan -->
                        <div>
                            <p class="font-semibold">Aturan Peralihan</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>
                                    Konstitusi ini disusun berdasarkan Keputusan Konferensi Tingkat Tinggi United Liberation Movement for West Papua I di Port Vila, Vanuatu 27 November – 3 Desember 2017 tentang Amandemen I Konstitusi United
                                    Liberation Movement for West Papua.
                                </li>
                                <li>
                                    Konstitusi ini disusun dengan merujuk kepada Keputusan Konferensi Tingkat Tinggi Luar Biasa United Liberation Movement for West Papua di Port Moresby, Papua Nugini 19 Desember 2019 tentang Peningkatan Status
                                    Kepengurusan United Liberation Movement for West Papua.
                                </li>
                                <li>
                                    Konstitusi ini disusun berdasarkan keputusan Sidang Tahunan III Komite Legislatif United Liberation Movement for West Papua di Port Numbay, West Papua 18 Oktober 2020 tentang Peningkatan Status Organisasi dengan
                                    Penetapan Undang-Undang Dasar Sementara.
                                </li>
                                <li>Untuk pertama kalinya Presiden dan Perdana Menteri diangkat oleh Sidang Tahunan III Komite Legislatif United Liberation Movement for West Papua.</li>
                                <li>
                                    Sebelum pembentukan kabinet, lembaga dan badan perangkat pemerintahan lainnya berdasarkan Konstitusi ini maka segala kekuasaan dijalankan oleh Presiden bersama Perdana Menteri dan dibantu oleh perangkat organisasi
                                    United Liberation Movement for West Papua.
                                </li>
                            </ol>
                        </div>

                        <!-- Aturan Penutup -->
                        <div>
                            <p class="font-semibold">Aturan Penutup</p>
                            <ol class="list-decimal pl-6 space-y-2">
                                <li>Konstitusi ini ditetapkan dan disahkan oleh Konferensi Tingkat Tinggi Luar Biasa United Liberation Movement for West Papua.</li>
                                <li>Konstitusi ini mulai berlaku sejak tanggal ditetapkan sampai berakhir di masa transisi.</li>
                            </ol>
                        </div>

                        <!-- Tanda tangan -->
                        <div class="flex justify-center mt-8">
                            <img src="/demo/const-ttd.png" alt="Tanda tangan KTT-LB ULMWP" class="max-w-md w-full" />
                        </div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('20')" />
                        <div class="flex-auto"></div>
                    </div>
                </StepPanel>

                <!-- Panel BAB I - XXI -->
                <!-- <StepPanel v-for="n in 21" :key="n" :value="n.toString()" v-slot="{ activateCallback }">
                    <div class="flex flex-col h-48">
                        <div class="border-2 border-dashed border-surface-200 dark:border-surface-700 rounded bg-surface-50 dark:bg-surface-950 flex-auto flex justify-center items-center font-medium text-lg">BAB {{ toRoman(n) }}</div>
                    </div>

                    <div class="flex pt-6 justify-between">
                        <Button v-if="n > 1" label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback((n - 1).toString())" />
                        <Button v-else label="Back" severity="secondary" icon="pi pi-arrow-left" @click="activateCallback('0')" />

                        <div class="flex-auto"></div>

                        <Button v-if="n < 21" label="Next" icon="pi pi-arrow-right" iconPos="right" @click="activateCallback((n + 1).toString())" />
                        <Button v-else label="Finish" severity="success" icon="pi pi-check" @click="alert('Semua BAB selesai!')" />
                    </div>
                </StepPanel> -->
            </StepPanels>
        </Stepper>
    </div>
</template>
