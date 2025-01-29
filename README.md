-- Pesan yang ingin dikirim
local messages = {
    "Selamat Hari Raya Cina!",
    "Gong Xi Fa Cai!",
    "Semoga Tahun Baru membawa kebahagiaan!",
    "Rayakan dengan penuh suka cita!"
}

-- Fungsi untuk mengirim pesan dengan efek
function sendMessage(message)
    SendPacket(2, "action|chat\nmessage|" .. message)
end

-- Fungsi untuk mengirim pesan dengan efek warna
function sendColoredMessage(message, color)
    SendPacket(2, "action|chat\nmessage|<color:" .. color .. ">" .. message)
end

-- Mengatur interval pengiriman pesan (dalam milidetik)
local interval = 5000 -- 5000 ms = 5 detik

-- Mengirim pesan secara berulang dengan efek
while true do
    for _, msg in ipairs(messages) do
        -- Mengirim pesan dengan efek warna
        sendColoredMessage(msg, "FF0000") -- Merah
        Sleep(1000) -- Tunggu 1 detik sebelum mengirim pesan berikutnya
    end
    Sleep(interval) -- Tunggu selama interval yang ditentukan
end
