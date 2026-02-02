###Depth first search

CREATE empty set Visited

CALL DFS_Visit(StartNode)

DFS_Visit(Node)
    ADD Node to Visited
    VISIT Node

    FOR each Neighbor of Node in Graph DO
        IF Neighbor not in Visited THEN
            CALL DFS_Visit(Neighbor)
        END IF
    END FOR
END DFS_Visit




#####Mini-max Minimax(Node, Depth, IsMax)

CREATE empty set Visited

CALL DFS_Visit(StartNode)

DFS_Visit(Node)
    ADD Node to Visited
    VISIT Node

    FOR each Neighbor of Node in Graph DO
        IF Neighbor not in Visited THEN
            CALL DFS_Visit(Neighbor)
        END IF
    END FOR
END DFS_Visit


#####GreedySearch(Graph, Start, Goal)

CREATE priority queue PQ

INSERT Start using heuristic

WHILE PQ not empty DO

    Node ← REMOVE lowest heuristic node
    PRINT Node
    IF Node = Goal THEN EXIT
    INSERT neighbors into PQ
END WHILE


#####Alpha beta pruning AlphaBeta(Node, Depth, α, β, IsMax)

IF Depth = 0 THEN RETURN value

IF IsMax THEN
    FOR each child DO
        α ← max(α, AlphaBeta(child))
        IF β ≤ α THEN BREAK
    END FOR
ELSE
    FOR each child DO
        β ← min(β, AlphaBeta(child))
        IF β ≤ α THEN BREAK
    END FOR
END IF
