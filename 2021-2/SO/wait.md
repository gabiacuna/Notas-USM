# Wait(null)

Bloquea al proceso padrea hasta que cualquiera de sus hijos haya terminado.

Si un proceso hijo termina antes de que el proceso padre llegue al wait, este se transforma en un proceso **zombie**, hata que su padre espere por el y sea liberado de la memoria.

Si un proceso padre no espera a que su proceso hijo termine, entonces el proceso hijo se transforma en huerfano y es asignado a init.