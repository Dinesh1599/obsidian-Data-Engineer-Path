FLATTEN is a table function that takes a VARIANT, OBJECT, or ARRAY column and produces a lateral view (that is, an inline view that contains correlations to other tables that precede it in the FROM clause).

Syntax:

FLATTEN( INPUT => <expr> [ , PATH => <constant_expr> ]
                         [ , OUTER => TRUE | FALSE ]
                         [ , RECURSIVE => TRUE | FALSE ]
                         [ , MODE => 'OBJECT' | 'ARRAY' | 'BOTH' ] )