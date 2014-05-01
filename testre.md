# Revision **1.1.1016** test report

## Toolbar
---
1. 在不同的 layout 間切換，很容易出現以下的錯誤訊息：
    ```
    i+nStartIndex:4
[sample_comm_vo.c]-[SAMPLE_COMM_VO_BindVpss]-301: failed with
    ```

    ``` 
    [lib_dvr_app.c]-[DVR_SetMosaicLayout]-2226: HI_MPI_VO_SetChnAttr(0) failed with 0xa00f806b! 
    ```
    ```
    HI_MPI_VDEC_ERROR
    ```
2. 切換至 layout 9 的第二頁，碼流沒進正確的 decoder，造成 `HI_MPI_VDEC_ERROR`。因為這個原因，當從 layout 9 切換至 layout 2 或 layout 1，畫面都沒辦法正常顯示

## Storage
---
1. 有 mount USB 隨身碟時，資訊會顯示錯誤，隨身碟的 model 會顯示成硬碟的 model 
    |     device | model       |
    | ---        | ---         |
    | 硬碟 sdb1 | hitachi xxx |
    | 隨身碟 sdc1 | hitachi xxx |
 
2. 隨身碟 mount 的順序在硬碟前，硬碟的 avaiable 容量會顯示成隨身碟的容量
     device | available(GB)
     --- | ---
     隨身碟 sdb1 | 0.11 
     硬碟 sdc1 | 0.11
3. 硬碟要格式化**兩次**才能錄影

4. 在 16 ch 全錄影的狀態下, 突然把硬碟的電源斷掉，console 一直出現錯誤訊息，造成 UI 當掉，目前只發生過一次
    ```
    **** [BKTREC] - basket_rec.c(2558): BKTREC_FlushWriteBuffer:failed write stream data. BID:1, b_pos:1047349, fpos:582684870
    ```
5. status 欄位只顯示 1、2、3，使用者會不知道是什麼意思 


## 其它
---
* 會出現 `HI_MPI_VDEC_ERROR` 的操作
  * camera search apply 後
  * 進入 floor plan 頁面有時會出現
  * 切換到 layout 1 太久
  * 在不同 layout 間切換

## 未來可改進
---
* 在設定 camera 的地方可以直接改 IP, 目前只能在 serach 完，apply/append 前修改。
