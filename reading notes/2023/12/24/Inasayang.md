Blink树，将单元格中的最右指针和节点的高健存储在一起；指针可以成对存储，每个单元格都有相应的指针，可以简化最右指针的处理

溢出页，数据增长超过默认页大小，允许节点以默认页大小为增量进行增长，分配一个页大小的扩展页，并在原始页中链接，溢出页需要额外的记录，因为会碎片化，第一个页ID存储在主页的头部，下一个页ID存储在上一个页ID头部
