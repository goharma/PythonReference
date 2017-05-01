```python
  
def _get_parser():
    # Creating parsers for commands
    # 1) Create a subparser
    # 2) Add options to that subparser
    # 3) Tell the subparser what function to execute when that command is passed in\
    # 4) Create the function


    parser = argparse.ArgumentParser()
    subparsers = parser.add_subparsers(help='sub-command help')

    #--------------------------------------------------------------------------
    #--------------------------------------------------------------------------
    # SUBPARSER TEMPLATE
    #--------------------------------------------------------------------------
    #--------------------------------------------------------------------------

    #--------------------------------------------------------------------------
    ## <command> Parser
    #--------------------------------------------------------------------------
    # 1) Create a subparser
    # parser_<command_name> = subparsers.add_parser('<command_name>', help='<Help text>')

    # 2) Add options to that subparser
    # parser_<command_name>.add_argument('--<positional arg 1>', help='Help text')
    # parser_<command_name>.add_argument('--<positional arg 2>', help='Help text')
    # ...
    # parser_<command_name>.add_argument('--<positional arg n>', help='Help text')

    # 3) Tell the subparser what function to execute when that command is passed in
    # parser_<command_name>.set_defaults(func=<function_name>)
        
        
# MAIN
parser = _get_parser()
args = parser.parse_args()

# parse the args and call whatever function was selected
args.func(args)
```