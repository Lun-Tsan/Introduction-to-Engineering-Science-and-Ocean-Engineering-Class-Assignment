This is a class Assignment aim to convert time domain signal to frequency domain.

I use Ethernet signal of my PC to plot the graph, raw data is the csv file, Colab code is at : https://colab.research.google.com/drive/1a2xAm10NjSKI5hy-NM2-ZtWehE-fmPvn?usp=sharing.

B11505050 洪綸燦

我最近剛好有在碰網路相關的東西，所以就把乙太網路的封包還有TCP錯誤量拿來分析，我是用wireshark這個app來擷取網卡相關的資訊，下載後選擇想聽的網路，等他累積數據後點選Statistics->I/O Graphs->Copy就可以複製出csv檔了。
此次選用的是以0.1秒為一個區間，聽了50分鐘(3000秒)所累積的數據，用python跑的code，raw data和colab連結在 "https://github.com/Lun-Tsan/Introduction-to-Engineering-Science-and-Ocean-Engineering-Class-Assignment"

從圖中可以見到，不管是封包量還是TCP錯誤量的peak都在0hz，代表訊號大部分時候都是有穩定的封包量，也有穩定的TCP錯誤，但是高frequency時的TCP錯誤量比封包量還要明顯，推測可能是有逾時的封包在固定的時間後要重傳，或是網路壅塞讓封包過了確認的時間，而他的等待時間就是在造成他在high frequeny比封包量明顯的原因。這個單純是猜測而已，而且實驗結果可能會因為每個人的電腦不一樣而有所不同，有興趣的人都可以去試試看~ 做這個作業之前我只了解要怎麼算，但是嘗試了這個主題之後為了要解讀數據，才了解它背後的意義，感覺學到了有趣的東西。
