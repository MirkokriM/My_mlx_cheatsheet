# Cheat Sheet: Funzioni di MLX per Linux

Di seguito è riportato un elenco completo delle funzioni di MLX per la gestione della grafica in Linux, insieme alle loro spiegazioni dettagliate.

## Funzione: mlx_init()
```c
#include <mlx.h>
void *mlx_init();
```
La funzione `mlx_init()` viene utilizzata per inizializzare la connessione con il server grafico. Restituisce un puntatore a una struttura dati che rappresenta la connessione appena creata.

## Funzione: mlx_new_window()
```c
#include <mlx.h>
void *mlx_new_window(void *mlx_ptr, int width, int height, char *title);
```
La funzione `mlx_new_window()` viene utilizzata per creare una nuova finestra grafica. Riceve come argomenti il puntatore alla connessione inizializzata con `mlx_init()`, la larghezza e l'altezza della finestra e il titolo della finestra. Restituisce un puntatore alla finestra creata.

## Funzione: mlx_pixel_put()
```c
#include <mlx.h>
void mlx_pixel_put(void *mlx_ptr, void *win_ptr, int x, int y, int color);
```
La funzione `mlx_pixel_put()` viene utilizzata per disegnare un pixel di colore specifico all'interno di una finestra. Riceve come argomenti il puntatore alla connessione, il puntatore alla finestra in cui disegnare, le coordinate (x, y) del pixel e il colore del pixel.

## Funzione: mlx_loop()
```c
#include <mlx.h>
int mlx_loop(void *mlx_ptr);
```
La funzione `mlx_loop()` viene utilizzata per avviare la gestione degli eventi per la connessione specificata. Questa funzione entra in un ciclo infinito che gestisce gli eventi come input da tastiera o mouse e aggiorna la finestra di conseguenza. Restituisce un valore solo quando la connessione viene chiusa.

## Funzione: mlx_destroy_window()
```c
#include <mlx.h>
void mlx_destroy_window(void *mlx_ptr, void *win_ptr);
```
La funzione `mlx_destroy_window()` viene utilizzata per distruggere una finestra precedentemente creata. Riceve come argomenti il puntatore alla connessione e il puntatore alla finestra da distruggere.

## Funzione: mlx_new_image()
```c
#include <mlx.h>
void *mlx_new_image(void *mlx_ptr, int width, int height);
```
La funzione `mlx_new_image()` viene utilizzata per creare una nuova immagine vuota con la larghezza e l'altezza specificate. Riceve come argomenti il puntatore alla connessione, la larghezza e l'altezza dell'immagine. Restituisce un puntatore all'immagine creata.

## Funzione: mlx_get_data_addr()
```c
#include <mlx.h>
char *mlx_get_data_addr(void *img_ptr, int *bits_per_pixel, int *size_line, int *endian);
```
La funzione `mlx_get_data_addr()` viene utilizzata per ottenere un puntatore ai dati dell'immagine. Riceve come arg

omenti il puntatore all'immagine restituito da `mlx_new_image()` e puntatori a interi per memorizzare il numero di bit per pixel, la lunghezza della riga di dati e l'endianess dei dati. Restituisce un puntatore ai dati dell'immagine.

## Funzione: mlx_put_image_to_window()
```c
#include <mlx.h>
void mlx_put_image_to_window(void *mlx_ptr, void *win_ptr, void *img_ptr, int x, int y);
```
La funzione `mlx_put_image_to_window()` viene utilizzata per copiare l'immagine specificata all'interno di una finestra. Riceve come argomenti il puntatore alla connessione, il puntatore alla finestra di destinazione, il puntatore all'immagine da copiare e le coordinate (x, y) in cui posizionare l'immagine.

## Funzione: mlx_key_hook()
```c
#include <mlx.h>
int mlx_key_hook(void *win_ptr, int (*funct_ptr)(), void *param);
```
La funzione `mlx_key_hook()` viene utilizzata per associare una funzione di gestione degli eventi alla pressione dei tasti in una finestra. Riceve come argomenti il puntatore alla finestra di destinazione, un puntatore alla funzione che verrà chiamata quando si verifica l'evento e un puntatore a un parametro opzionale che può essere passato alla funzione.

## Funzione: mlx_mouse_hook()
```c
#include <mlx.h>
int mlx_mouse_hook(void *win_ptr, int (*funct_ptr)(), void *param);
```
La funzione `mlx_mouse_hook()` viene utilizzata per associare una funzione di gestione degli eventi ai movimenti del mouse in una finestra. Riceve come argomenti il puntatore alla finestra di destinazione, un puntatore alla funzione che verrà chiamata quando si verifica l'evento e un puntatore a un parametro opzionale che può essere passato alla funzione.

## Funzione: mlx_loop_hook()
```c
#include <mlx.h>
int mlx_loop_hook(void *mlx_ptr, int (*funct_ptr)(), void *param);
```
La funzione `mlx_loop_hook()` viene utilizzata per associare una funzione di gestione degli eventi di ciclo al loop principale di MLX. Questa funzione viene chiamata in ogni iterazione del loop, consentendo di eseguire azioni aggiuntive durante l'esecuzione del programma. Riceve come argomenti il puntatore alla connessione, un puntatore alla funzione che verrà chiamata ad ogni iterazione e un puntatore a un parametro opzionale che può essere passato alla funzione.

## Funzione: mlx_clear_window()
```c
#include <mlx.h>
void mlx_clear_window(void *mlx_ptr, void *win_ptr);
```
La funzione `mlx_clear_window()` viene utilizzata per cancellare il contenuto di una finestra specificata, riempiendola con il colore di sfondo predefinito. Riceve come argomenti il puntatore alla connessione e il puntatore alla finestra da cancellare.

## Funzione: mlx_string_put()
```c
#include <mlx.h>
void mlx_string_put(void *mlx_ptr, void *win_ptr, int x, int y, int color, char *string);
```
La funzione `mlx_string_put()` viene utilizzata per disegnare una stringa di testo

 all'interno di una finestra. Riceve come argomenti il puntatore alla connessione, il puntatore alla finestra di destinazione, le coordinate (x, y) in cui posizionare la stringa, il colore del testo e la stringa stessa.

## Funzione: mlx_mouse_hide()
```c
#include <mlx.h>
void mlx_mouse_hide(void);
```
La funzione `mlx_mouse_hide()` viene utilizzata per nascondere il cursore del mouse.

## Funzione: mlx_mouse_show()
```c
#include <mlx.h>
void mlx_mouse_show(void);
```
La funzione `mlx_mouse_show()` viene utilizzata per mostrare il cursore del mouse.
