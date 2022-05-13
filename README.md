# Example.Umbrella

run `mix release --env=prod --verbose` then `_build/dev/rel/example_umbrella/bin/example_umbrella console`
to see following error:

```
[info] Application honeybadger exited: Honeybadger.start(:normal, []) returned an error: shutdown: failed to start child: Honeybadger.Client
    ** (EXIT) an exception was raised:
        ** (CaseClauseError) no case clause matching: {:error, {{:noproc, {:gen_server, :call, [:hackney_telemetry_sup, {:start_child, %{id: {:hackney_telemetry_worker, [:hackney_pool, Honeybadger.Client, :take_rate]}, start: {:hackney_telemetry_worker, :start_link, [[metric: [:hackney_pool, Honeybadger.Client, :take_rate]]]}}}, :infinity]}}, {:child, :undefined, Honeybadger.Client, {:hackney_pool, :start_link, [Honeybadger.Client, [name: Honeybadger.Client, max_connections: 20]]}, :permanent, 10000, :worker, [:hackney_pool]}}}
            (hackney) /home/massa/avvo/devbox/example_umbrella/deps/hackney/src/hackney_pool.erl:218: :hackney_pool.do_start_pool/2
            (hackney) /home/massa/avvo/devbox/example_umbrella/deps/hackney/src/hackney_pool.erl:142: :hackney_pool.start_pool/2
            (honeybadger) lib/honeybadger/client.ex:101: Honeybadger.Client.init/1
Initial commit
            (stdlib) gen_server.erl:374: :gen_server.init_it/2
            (stdlib) gen_server.erl:342: :gen_server.init_it/6
            (stdlib) proc_lib.erl:249: :proc_lib.init_p_do_apply/3
{"Kernel pid terminated",application_controller,"{application_start_failure,honeybadger,{{shutdown,{failed_to_start_child,'Elixir.Honeybadger.Client',{{case_clause,{error,{{noproc,{gen_server,call,[hackney_telemetry_sup,{start_child,#{id => {hackney_telemetry_worker,[hackney_pool,'Elixir.Honeybadger.Client',take_rate]},start => {hackney_telemetry_worker,start_link,[[{metric,[hackney_pool,'Elixir.Honeybadger.Client',take_rate]}]]}}},infinity]}},{child,undefined,'Elixir.Honeybadger.Client',{hackney_pool,start_link,['Elixir.Honeybadger.Client',[{name,'Elixir.Honeybadger.Client'},{max_connections,20}]]},permanent,10000,worker,[hackney_pool]}}}},[{hackney_pool,do_start_pool,2,[{file,\"/home/massa/avvo/devbox/example_umbrella/deps/hackney/src/hackney_pool.erl\"},{line,218}]},{hackney_pool,start_pool,2,[{file,\"/home/massa/avvo/devbox/example_umbrella/deps/hackney/src/hackney_pool.erl\"},{line,142}]},{'Elixir.Honeybadger.Client',init,1,[{file,\"lib/honeybadger/client.ex\"},{line,101}]},{gen_server,init_it,2,[{file,\"gen_server.erl\"},{line,374}]},{gen_server,init_it,6,[{file,\"gen_server.erl\"},{line,342}]},{proc_lib,init_p_do_apply,3,[{file,\"proc_lib.erl\"},{line,249}]}]}}},{'Elixir.Honeybadger',start,[normal,[]]}}}"}
Kernel pid terminated (application_controller) ({application_start_failure,honeybadger,{{shutdown,{failed_to_start_child,'Elixir.Honeybadger.Client',{{case_clause,{error,{{noproc,{gen_server,call,[hac
```
