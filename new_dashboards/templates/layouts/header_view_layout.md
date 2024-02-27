# Documentação do Layout Header View

O layout `Header View` tem a característica de exibir um cabeçalho com título e subtítulo no topo da página, chamado de `Section Title`, e um grid container no restante, chamado de `Section Grid`

O layout master `header_view_layout` utiliza as seguintes máscaras de estilo:
- `no_base_style_mask`: Remove background, bordas, margens e paddings
- `general_container_style_mask`: Adiciciona 12px de padding para todos os lados e remove `pointer-events` e `cursor`, já que o template trata-se de um layout e não executa nenhuma ação.

`header_view_layout` divide as duas seções na proporção `80px` para o `Section Title` e `calc(100% - 80px)` para o `Section Grid`

O conteúdo de `Section Title` é posicionado em `center start` (centralizado horizontalmente e justificado à esquerda) enquanto o conteúdo de `Section Grid` 

## Árvore de Templates

- header_view_layout
    - header_view_layout_section_fields
    - header_view_layout_section_title
        - primary_info_component_part
        - secondary_info_component_part

## Parâmetros

| Parâmetro                     | Tipo                  | Padrão                         |
|-------------------------------|-----------------------|--------------------------------|
| title                         | String                | Opcional                       |
| subtitle                      | String                | Opcional                       |
| regular_grid_template         | Enum\<Grid Template\> | `1_col_auto_row_grid_template` |
| grid_template_on_mediumscreen | Enum\<Grid Template\> | `1_col_auto_row_grid_template` |
| grid_template_on_smallscreen  | Enum\<Grid Template\> | `1_col_auto_row_grid_template` |
| set_height_100                | Boolean               | `true`                         |
| fields                        | Card[]                | Opcional                       |

## Grid Template Enums

| Identificador                | Grid Template                                   | Auto Row          |
|------------------------------|-------------------------------------------------|-------------------|
| auto_wrapper_grid_template   |                                   `100% / 100%` |            `100%` |
| 1_col_auto_row_grid_template |                       `auto / calc(100% - 6px)` |            `auto` |
| 2_col_auto_row_grid_template |             `auto / repeat(2, calc(50% - 6px))` |            `auto` |
| 2_col_half_row_grid_template | `calc(50% - 3px) / repeat(2, calc( 50% - 3px))` | `calc(50% - 3px)` |